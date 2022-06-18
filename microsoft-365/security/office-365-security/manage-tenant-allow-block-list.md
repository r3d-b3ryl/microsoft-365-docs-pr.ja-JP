---
title: テナント許可/ブロック一覧の許可とブロックを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: セキュリティ ポータルのテナント許可/ブロック一覧で、許可とブロックを管理する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dc32e6827e9751dc72d28b8eff79d1966f43f646
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2022
ms.locfileid: "66159845"
---
# <a name="manage-your-allows-and-blocks-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧で許可とブロックを管理する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスが含まれているMicrosoft 365組織では、Exchange Onlineメールボックスがない場合は、EOP フィルターの判定に同意しない可能性があります。 たとえば、適切なメッセージが無効 (誤検知) としてマークされたり、不適切なメッセージが許可されたり (偽陰性) されたりすることがあります。

Microsoft 365 Defender ポータルのテナント許可/ブロック リストを使用すると、Microsoft 365フィルターの判定を手動でオーバーライドできます。 テナント許可/ブロック リストは、受信メッセージのメール フロー中 (組織内メッセージには適用されません)、ユーザーがクリックした時点で使用されます。 次の種類のオーバーライドを指定できます。

- ブロックする URL。
- ブロックするファイル。
- ブロックする送信者の電子メールまたはドメイン。
- 許可またはブロックするスプーフィングされた送信者。 [スプーフィング インテリジェンス分析情報](learn-about-spoof-intelligence.md)の許可またはブロックの判定をオーバーライドすると、スプーフィングされた送信者は、テナント許可/ブロックリストの [**スプーフィング**] タブにのみ表示される手動の許可エントリまたはブロック エントリになります。 スプーフィング インテリジェンスによって検出される前に、スプーフィングされた送信者の許可エントリまたはブロック エントリを手動で作成することもできます。
- 許可する URL
- 許可するファイル。
- 許可する送信者の電子メールまたはドメイン。

この記事では、Microsoft 365 Defender ポータルまたは PowerShell (Exchange Online のメールボックスを持つMicrosoft 365組織の PowerShell をExchange Online、スタンドアロン EOP PowerShell を使用しない組織のテナント許可/ブロック リストでエントリを構成する方法について説明します。Exchange Online メールボックス)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[テナント許可/ブロック リスト**] ページに直接移動するには、次を使用<https://security.microsoft.com/tenantAllowBlockList>します。

- ファイルの SHA256 ハッシュ値を使用してファイルを指定します。 Windowsでファイルの SHA256 ハッシュ値を見つけるには、コマンド プロンプトで次のコマンドを実行します。

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  値の例は `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`. Perceptual hash (pHash) 値はサポートされていません。

- 送信者、URL、ファイル ハッシュの場合、テナント許可/ブロック リストでは、許可とブロックの両方に対してそれぞれ 500 エントリが許可され、合計で 1,000 エントリになります。 スプーフィング (スプーフィングされた送信者) の場合、許可されるエントリの合計数は 1024 です。

- 各エントリの最大文字数は次のとおりです。
  - ファイル ハッシュ = 64
  - URL = 250

- エントリは 30 分以内にアクティブにする必要があります。

- 既定では、テナント許可/ブロック リストのエントリは 30 日後に期限切れになります。 日付を指定するか、期限切れにならないように設定できます (エントリのブロックの種類の場合)。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめExchange Online でアクセス許可を割り当てる必要があります。
  - テナント許可/ブロック リストの値を追加および削除するには、次のメンバーである必要があります。
    - **組織の管理** または **セキュリティ管理者** の役割グループ (**セキュリティ管理者ロール**)
    - **Security Operator** ロール グループ (**テナント AllowBlockList Manager**)。
  - テナント許可/ブロック リストへの読み取り専用アクセスの場合は、次のメンバーである必要があります。
    - **グローバル リーダー**  の役割グループ
    - **セキュリティ 閲覧者** の役割グループ
    - **ビューのみの構成** 役割グループ

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 *および* Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

## <a name="configure-the-tenant-allowblock-list"></a>テナント許可/ブロック リストを構成する

### <a name="use-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを使用する

Microsoft 365 Defender ポータルの [ルール **] セクションの** <https://security.microsoft.com>[**ポリシー&ルール** \> **脅威ポリシー** \> **テナント許可/ブロック リスト**] に移動します。 **[テナント許可/ブロック リスト**] ページに直接移動するには、次を使用<https://security.microsoft.com/tenantAllowBlockList>します。

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell"></a>PowerShell またはスタンドアロンの EOP PowerShell Exchange Online使用する

電子メールを許可またはブロックするには、「 [テナント許可/ブロック リストを使用して電子メールを許可またはブロックする」を参照してください](allow-block-email-spoof.md)。

ファイルを許可またはブロックするには、「 [テナント許可/ブロック リストを使用してファイルを許可またはブロックする」を参照してください](allow-block-files.md)。

URL を許可またはブロックするには、「 [テナント許可/ブロック リストを使用して URL を許可またはブロックする」を参照してください](allow-block-urls.md)。

### <a name="what-to-expect-after-you-add-an-allow-or-block-entry"></a>許可エントリまたはブロック エントリを追加した後に必要なもの

申請ポータルまたはテナント許可/ブロック リストのブロック エントリを使用して許可エントリを追加した後、エントリはすぐに動作を開始する必要があります。

システムが許可またはブロックについて学習したかどうかを確認するために、エントリの有効期限を 30 日後に自動的に設定することをお勧めします。 そうでない場合は、システムに学習にさらに 30 日間を与えるために、別のエントリを作成する必要があります。

## <a name="view-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック リストのエントリを表示する

1. Microsoft 365 Defender ポータルの [ルール **] セクションの** <https://security.microsoft.com>[**ポリシー&ルール** \> **脅威ポリシー** \> **テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. 目的のタブを選択します。 使用可能な列は、選択したタブによって異なります。

   - **送信者**:
     - **値**: 送信者のドメインまたは電子メール アドレス。
     - **アクション**: 値 **Allow** または **Block**。
     - **変更者**
     - **最終更新日時**
     - **[削除]**
     - **注**
   - 「**スプーフィング**」
     - **偽のユーザー**
     - **インフラストラクチャの送信**
     - **スプーフィングの種類**: 値 **内部** または **外部**。
     - **アクション**: 値 **[ブロック]** または **[許可] を指定** します。
   - **URL**:
     - **値**: URL。
     - **アクション**: 値 **Allow** または **Block**。
     - **変更者**
     - **最終更新日時**
     - **[削除]**
     - **注**
   - **ファイル**
     - **値**: ファイル ハッシュ。
     - **アクション**: 値 **Allow** または **Block**。
     - **変更者**
     - **最終更新日時**
     - **[削除]**
     - **注**

   列見出しをクリックすると、昇順または降順で並べ替えることができます。

   [ **グループ]** をクリックして結果をグループ化できます。 使用可能な値は、選択したタブによって異なります。

   - **送信者**: **アクション** で結果をグループ化できます。
   - **スプーフィング**: **アクション** または **スプーフィングの種類** で結果をグループ化できます。
   - **URL**: **アクション** で結果をグループ化できます。
   - **ファイル**: **アクション** で結果をグループ化できます。

   [ **検索**] をクリックし、値の全部または一部を入力し、Enter キーを押して特定の値を見つけます。 完了したら、[検索のクリア] アイコンをクリックします ![。](../../media/m365-cc-sc-close-icon.png) **検索をクリアします**。

   [ **フィルター]** をクリックして結果をフィルター処理します。 **表示されるフィルター** ポップアップで使用できる値は、選択したタブによって異なります。

   - [**Senders (送信者)**]
     - **操作**
     - **有効期限が切れない**
     - **最終更新日**
     - **[削除]**
   - 「**スプーフィング**」
     - **操作**
     - **スプーフィングの種類**
   - **Url**
     - **操作**
     - **有効期限が切れない**
     - **最終更新日**
     - **[削除]**
   - **ファイル**
     - **操作**
     - **有効期限が切れない**
     - **最終更新日時**
     - **[削除]**

   完了したら、**[適用]** をクリックします。 既存のフィルターをクリアするには、[ **フィルター**] をクリックし、表示される **[フィルター** ] ポップアップで [ **フィルターのクリア**] をクリックします。

## <a name="modify-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック リストのエントリを変更する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. 変更するエントリの種類を含むタブを選択します。
   - [**Senders (送信者)**]
   - 「**スプーフィング**」
   - **Url**
   - **ファイル**

3. 変更するエントリを選択し、[編集] アイコンをクリックします ![。](../../media/m365-cc-sc-edit-icon.png) **編集**。 ポップアップで変更できる値は、前の手順で選択したタブによって異なります。
   - [**Senders (送信者)**]
     - **期限切れ** や有効期限を設定しないでください。
     - **省略可能なメモ**
   - 「**スプーフィング**」
     - **アクション**: 値を **[許可** ] または [ **ブロック**] に変更できます。
   - **Url**
     - **期限切れ** や有効期限を設定しないでください。
     - **省略可能なメモ**
   - **ファイル**
     - **期限切れ** や有効期限を設定しないでください。
     - **省略可能なメモ**

    送信者、URL、ファイルの値は、ブロックされたエントリに対してのみ期限切れになることはありません。 

4. 完了したら、**[保存]** をクリックします。

> [!NOTE]
> 延長できるのは、作成日から最大で 30 日間です。 ブロックは最大 90 日間延長できますが、許可とは異なり、[期限切れなし] に設定することもできます。

## <a name="remove-entries-from-the-tenant-allowblock-list"></a>テナント許可/ブロック リストからエントリを削除する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. 削除するエントリの種類を含むタブを選択します。
   - [**Senders (送信者)**]
   - 「**スプーフィング**」
   - **Url**
   - **ファイル**

3. 削除するエントリを選択し、[削除] アイコンをクリックします ![。](../../media/m365-cc-sc-delete-icon.png) **Delete**

4. 表示される警告ダイアログで、[削除] をクリック **します**。

## <a name="related-articles"></a>関連記事

- [テナント許可/ブロック リスト内のファイルを許可またはブロックする](allow-block-files.md)
- [テナントの許可/ブロック一覧で電子メールを許可またはブロックする](allow-block-email-spoof.md)
- [テナント許可/ブロック リストの URL を許可またはブロックする](allow-block-urls.md)