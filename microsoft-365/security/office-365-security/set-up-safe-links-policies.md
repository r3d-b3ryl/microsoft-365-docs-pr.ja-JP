---
title: Microsoft Defender for Office 365 で安全なリンク ポリシーを設定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、Microsoft Defender for Office 365のセーフ リンク ポリシーとグローバルセーフ リンク設定を表示、作成、変更、削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 48e873550c83154827d7deaa430b75d82ff80acc
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67087267"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 で安全なリンク ポリシーを設定する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。 Outlook の Safelinks に関する情報を探しているホーム ユーザーの場合は、 [高度な Outlook.com セキュリティ](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)に関するページを参照してください。

[Microsoft Defender for Office 365](defender-for-office-365.md)の安全なリンクは、メール フロー内の受信メール メッセージの URL スキャンと、電子メール メッセージやその他の場所での URL とリンクのクリック確認の時間を提供します。 詳細については、「[Microsoft Defender for Office 365のセーフ リンク](safe-links.md)」を参照してください。

既定のセーフ リンク ポリシーはありませんが、 **組み込みの保護** プリセット セキュリティ ポリシーは、すべての受信者 (カスタムのセーフ リンクまたは Standard または Strict プリセットのセキュリティ ポリシーで定義されていないユーザー) に安全なリンク保護を提供します。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。

この記事の手順を使用して、特定のユーザー、グループ、またはドメインに適用されるセーフ リンク ポリシーを作成することもできます。

> [!NOTE]
>
> セーフ リンク ポリシー **の外部** でセーフ リンク保護のグローバル設定で、[次の URL をブロックする] の一覧を構成します。 手順については、「[Microsoft Defender for Office 365のセーフ リンクのグローバル設定を構成](configure-global-settings-for-safe-links.md)する」を参照してください。
>
> 管理者は、安全なリンクのさまざまな構成設定を検討する必要があります。 使用できるオプションの 1 つは、ユーザーが識別できる情報を安全なリンクに含める方法です。 この機能により、セキュリティ運用 (SecOps) チームは潜在的なユーザー侵害を調査し、修正措置を講じ、コストのかかる侵害を制限できます。

セーフ リンク ポリシーは、Microsoft 365 Defender ポータルまたは PowerShell で構成できます (Exchange Online にメールボックスがある適格な Microsoft 365 組織の場合は Exchange Online PowerShell で、Exchange Online メールボックスがないが、Microsoft Defender for Office 365アドオンがある組織の場合はスタンドアロンEOP PowerShell サブスクリプションです)。

安全なリンク ポリシーの基本的な要素は次のとおりです。

- **安全なリンク ポリシー**: セーフ リンク保護を有効にし、リアルタイム URL スキャンを有効にし、メッセージを配信する前にリアルタイム スキャンが完了するのを待機するかどうかを指定し、内部メッセージのスキャンをオンにし、ユーザーが URL をクリックしたかどうかを追跡するかどうかを指定し、ユーザーが元の URL をクリックできるかどうかを指定します。
- **安全なリンク規則**: 優先度フィルターと受信者フィルター (ポリシーが適用されるユーザー) を指定します。

Microsoft 365 Defender ポータルでセーフ リンク ポリシーを管理する場合、これら 2 つの要素の違いは明らかではありません。

- 安全なリンク ポリシーを作成するときは、実際には、安全なリンク規則と、関連付けられている安全なリンク ポリシーを同時に作成し、両方に同じ名前を使用します。
- 安全なリンク ポリシーを変更する場合、名前、優先順位、有効/無効の切り替え、そして受信者フィルターに関連する設定の変更は、実際には安全なリンク ルールを変更しています。 他のすべての設定は、関連付けられている安全なリンク ポリシーを変更します。
- 安全なリンク ポリシーを削除すると、安全なリンク規則と関連する安全なリンク ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事の後半の「[PowerShell またはスタンドアロンの EOP PowerShell Exchange Online使用して安全なリンク ポリシーを構成する](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies)」セクションを参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[安全なリンク**] ページに直接移動するには、 <https://security.microsoft.com/safelinksv2>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行するには、アクセス許可を割り当てる必要があります。
  - セーフ リンク ポリシーを作成、変更、削除するには、Microsoft 365 Defender ポータルの **組織管理** または **セキュリティ管理者** の役割グループのメンバー **であり**、Exchange Onlineの **組織管理** 役割グループのメンバーである必要があります。
  - セーフ リンク ポリシーに対する読み取り専用アクセスの場合は、 **グローバル リーダー** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)と[Exchange Onlineのアクセス許可に関するページを参照](/exchange/permissions-exo/permissions-exo)してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可 _と_、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  . - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の **表示専用組織管理** 役割グループでは、この機能に対する読み取り専用アクセス権も付与されます。

- セーフ リンク ポリシーの推奨設定については、「 [セーフ リンク ポリシーの設定](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)」を参照してください。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 6 時間を許可します。

- [新機能はMicrosoft Defender for Office 365に継続的に追加されています](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)。 新機能が追加されると、既存のセーフ リンク ポリシーの調整が必要になる場合があります。

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>Microsoft 365 Defender ポータルを使用してセーフ リンク ポリシーを作成する

Microsoft 365 Defender ポータルでカスタムセーフ リンク ポリシーを作成すると、安全なリンク規則と関連付けられた安全なリンク ポリシーが同時に作成され、両方に同じ名前が使用されます。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[安全なリンク]** の順に移動します。 **[安全なリンク**] ページに直接移動するには、 <https://security.microsoft.com/safelinksv2>.

2. [ **安全なリンク** ] ページで、[作成] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **Create**。

3. **[新しい安全なリンク ポリシー]** ウィザードが開きます。 [ **ポリシーの名前]** ページで、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。
   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **[ユーザーとドメイン]** ページで、ポリシーを適用する内部の受信者を特定します (受信者条件)。
   - **ユーザー**: 指定されたメールボックス、メール ユーザー、またはメール連絡先。
   - **グループ**: 
     - 指定された配布グループまたはメールが有効なセキュリティ グループのメンバー。
     - 指定した Microsoft 365 グループ。
   - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   同じ条件の複数の値は、OR ロジックを使用します (たとえば _\<recipient1\>_ または _\<recipient2\>_)。異なる条件では AND ロジックを使用します (たとえば _\<recipient1\>_ および _\<member of group 1\>_)。

   - **これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。設定と動作は、条件とまったく同じです。

   > [!IMPORTANT]
   > 複数の異なる種類の条件や例外は加算されません。包括的です。 ポリシーは、指定された _すべての_ 受信者フィルターに一致する受信者 _にのみ_ 適用されます。 たとえば、次の値を使用してポリシーで受信者フィルター条件を構成します:
   >
   > - 受信者は次のとおりです: romain@contoso.com
   > - 受信者が次のメンバーの場合: Executive
   >
   > ポリシーは、Executive グループのメンバーである場合 _にのみ_、romain@contoso.com に適用されます。 グループのメンバーでない場合、ポリシーは適用されません。
   >
   > 同様に、同じ受信者フィルターをポリシーの例外として使用する場合、受信者が Executive グループのメンバーでもある場合 _にのみ_、ポリシーは romain@contoso.com に適用されません。 グループのメンバーでない場合でも、ポリシーは適用されます。

   完了したら、**[次へ]** をクリックします。

5. URL **&表示される [保護設定]** ページで、次の設定を構成します。

   - **[電子メール] セクション内の潜在的に悪意のある URL に対するアクション** :
     - **オン: ユーザーがメール内のリンクをクリックすると、既知の悪意のあるリンクの一覧が安全なリンクでチェック** されます。このオプションを選択すると、電子メール メッセージ内のリンクに対するセーフ リンク保護が有効になります。 このオプションを選択すると、次の設定を使用できます。
       - **組織内で送信された電子メール メッセージに安全なリンクを適用** する: 内部送信者と内部受信者の間のメッセージに安全なリンク ポリシーを適用するには、このオプションを選択します。
       - **疑わしいリンクとファイルを指すリンクのリアルタイム URL スキャンを適用** する: 電子メール メッセージ内のリンクのリアルタイム スキャンを有効にするには、このオプションを選択します。 このオプションを選択すると、次の設定を使用できます。
         - **メッセージを配信する前に URL スキャンが完了するまで待ちます:メッセージを配信する前** に、リアルタイムの URL スキャンが完了するまで待機するには、このオプションを選択します。
       - **URL を書き換えないでください。SafeLinks API 経由でのみチェックを行います**。URL の折り返しを防ぐには、このオプションを選択します。 安全なリンクは、URL クリック時に API を介して排他的に呼び出されます。これは、それをサポートする Outlook クライアントによって行われます。

       - **[電子メール] セクションで次の URL を書き換えないでください** 。 **[管理 ] (nn) URL を** クリックして、セーフ リンクによってブロックされる特定の URL へのアクセスを許可します。

         > [!NOTE]
         > [次の URL を書き換えない] リストのエントリは、メール フロー中に安全なリンクによってスキャンまたはラップされません。 [テナント許可/禁止リストで URL エントリを許可する](allow-block-urls.md#create-allow-url-entries) を使用して、メール フロー _および_ クリック時に安全なリンクで URL がスキャンされたり、ラップされないようにします。

     1. 表示されるポップアップ **を書き換えない URL の管理** で、[URL の追加] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **URL を追加します**。
     2. 表示される **[URL の追加]** ポップアップで、目的の URL または値を入力し、ボックスの下に表示されるエントリを選択して、[ **保存**] をクリックします。 必要な回数だけこの手順を繰り返します。

        エントリ構文については、「 [次の URL を書き換えない」の一覧のエントリ構文に関するページを参照してください](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。

        エントリを削除するには、 ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) エントリの横に表示されます。

        完了したら、**[保存]** をクリックします。

     3. ポップアップを **書き換えないように URL の管理に** 戻り、エントリの一覧で **[完了]** をクリックするか、メンテナンスを行います。

        リストからエントリを削除するには、[検索] アイコンを ![使用します。](../../media/m365-cc-sc-search-icon.png) **検索** ボックスでエントリを検索します。

        1 つのエントリを選択するには、[ **URL** ] 列の値をクリックします。

        複数のエントリを 1 つずつ選択するには、値の左側にある空白領域をクリックします。

        すべてのエントリを 1 つで選択するには、 **URL** 列ヘッダーの左側にある空白領域をクリックします。

        1 つ以上のエントリが選択されている状態で、 ![[URL の追加] アイコン。](../../media/m365-cc-sc-create-icon.png) または ![[削除] アイコン。](../../media/m365-cc-sc-delete-icon.png) アイコンが表示されます。

        完了したら、[**完了**] をクリックします。

   - **Microsoft Teams セクションの潜在的に悪意のある URL に対するアクション** :
     - **オン: [安全なリンク] は、ユーザーが [Microsoft Teamsでリンクをクリックすると、既知の悪意のあるリンクの一覧をチェックします**。このオプションを選択すると、Teams のリンクに対するセーフ リンク保護が有効になります。 この設定を有効にするには、最大で 24 時間かかる場合があることに注意してください。

     > [!NOTE]
     > 現在、Microsoft Teams のセーフ リンク保護は、Microsoft 365 GCC High または Microsoft 365 DoD では使用できません。

   - **Microsoft Office アプリの潜在的に悪意のある URL に対するアクション** セクション:
     - **オン: [セーフ リンク] は、ユーザーが Microsoft Office アプリでリンクをクリックしたときに既知の悪意のあるリンクの一覧をチェックします**。このオプションを選択すると、サポートされている Office デスクトップ、モバイル、および Web アプリ内のファイル内のリンクに対するセーフ リンク保護が有効になります。

   - **[保護設定] セクションをクリックします** 。
     - **ユーザーのクリックを追跡する**: このオプションを選択したままにして、追跡ユーザーが URL をクリックできるようにします。 このオプションを選択すると、次のオプションを使用できます。
       - **ユーザーが元の URL までクリック** できるようにする: [警告ページ](safe-links.md#warning-pages-from-safe-links)でユーザーが元の URL までクリックするのをブロックするには、このオプションをオフにします。
       - **通知ページと警告ページに組織のブランドを表示** する: カスタマイズされたブランド化の詳細については、「 [組織の Microsoft 365 テーマをカスタマイズする](../../admin/setup/customize-your-organization-theme.md)」を参照してください。

   これらの設定の詳細については、次を参照してください。

   - [電子メール メッセージのセーフ リンク設定](safe-links.md#safe-links-settings-for-email-messages)。
   - [Microsoft Teamsのセーフ リンク設定](safe-links.md#safe-links-settings-for-microsoft-teams)。
   - [Office アプリのセーフ リンク設定](safe-links.md#safe-links-settings-for-office-apps)。
   - [安全なリンク ポリシーで保護の設定をクリックする](safe-links.md#click-protection-settings-in-safe-links-policies)

   Standard ポリシーと Strict ポリシー設定の推奨値の詳細については、「 [セーフ リンク ポリシーの設定](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)」を参照してください。

   完了したら、**[次へ]** をクリックします。

6. 表示される **[通知]** ページで、[**ユーザーに通知する方法**] で次のいずれかの値を選択します。
   - **既定の通知テキストを使用する**
   - **カスタム通知テキストを使用** する: この値を選択すると、次の設定が表示されます。
     - **自動ローカライズに Microsoft Translator を使用する**
     - **カスタム通知テキスト**: このボックスにカスタム通知テキストを入力します (長さは 200 文字を超えることはできません)。

   完了したら、**[次へ]** をクリックします。

7. 表示された **[レビュー]** ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、**[送信]** をクリックします。

8. 表示された [確認]ページで、**[完了]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>Microsoft 365 Defender ポータルを使用してセーフ リンク ポリシーを表示する

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[安全なリンク]** の順に移動します。 **[安全なリンク**] ページに直接移動するには、 <https://security.microsoft.com/safelinksv2>.

2. **[安全なリンク**] ページの [安全なリンク] ポリシーの一覧に次のプロパティが表示されます。
   - **名前**
   - **状態**
   - **優先度**

3. ポリシーの名前をクリックして選択すると、ポリシー設定がポップアウトで表示されます。

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>Microsoft 365 Defender ポータルを使用してセーフ リンク ポリシーを変更する

1. Microsoft 365 Defender ポータルで、[**ポリシー&ルール** \> **の脅威ポリシー** \> **ポリシー**] セクション **の [安全なリンク**] に\>移動します。

2. [ **安全なリンク** ] ページで、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 設定の詳細については、この記事の「[Microsoft 365 Defender ポータルを使用してセーフ リンク ポリシーを作成する](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)」セクションを参照してください。

ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションをご覧ください。

### <a name="enable-or-disable-safe-links-policies"></a>セーフ リンク ポリシーを有効または無効にする

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[安全なリンク]** の順に移動します。 **[安全なリンク**] ページに直接移動するには、 <https://security.microsoft.com/safelinksv2>.

2. [ **安全なリンク** ] ページで、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。
   - **ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。
   - **ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。

5. ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。

### <a name="set-the-priority-of-safe-links-policies"></a>安全なリンク ポリシーの優先度を設定します

既定では、セーフ リンクには、作成された順序に基づく優先順位が与えられます (新しいポリシーは古いポリシーよりも優先順位が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

ポリシーの優先度を変更するには、ポリシーのプロパティで [**優先度を上げる**] または [**優先度を下げる**] をクリックします (Microsoft 365 Defender ポータルの [**優先度**] の数値を直接変更することはできません)。ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。

**注**:

- Microsoft 365 Defender ポータルでは、セーフ リンク ポリシーの優先度は、作成後にのみ変更できます。 PowerShell では、安全なリンク規則を作成するときに既定の優先度をオーバーライドできます (既存のルールの優先度に影響を与える可能性があります)。
- セーフ リンク ポリシーは、表示された順序で処理されます (最初のポリシーの **優先度** の値は 0 です)。 優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[安全なリンク]** の順に移動します。 **[安全なリンク**] ページに直接移動するには、 <https://security.microsoft.com/safelinksv2>.

2. [ **安全なリンク** ] ページで、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。
   - **優先度** の値が **0** のポリシーでは、**[優先度を下げる]** オプションのみ利用可能です。
   - **優先度** 値が最低のポリシー (例: **3**) では、**[優先度を下げる]** オプションのみ利用可能です。
   - 3 つ以上のポリシーがある場合、優先度の値が最も高いポリシーと最も低いポリシーの間では、**[優先度を上げる]** と **[優先度を下げる]** の両方のオプションが利用可能です。

   ![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。

4. 完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>Microsoft 365 Defender ポータルを使用してセーフ リンク ポリシーを削除する

1. Microsoft 365 Defender ポータルで、[ポリシー] セクション **の [Email & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **の安全なリンク****]** に移動します。

2. [ **安全なリンク** ] ページで、名前をクリックして一覧からポリシーを選択します。 表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作]](../../media/m365-cc-sc-more-actions-icon.png) アイコンをクリックします。 **[その他の操作]** \> ![[ポリシーの削除]](../../media/m365-cc-sc-delete-icon.png) アイコン **[ポリシーの削除]** の順にクリックします。

3. 確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>PowerShell またはスタンドアロン EOP PowerShell Exchange Onlineを使用してセーフ リンク ポリシーを構成する

前述のように、安全なリンク ポリシーは、安全なリンク ポリシーと安全なリンク規則で構成されています。

PowerShell では、安全なリンク ポリシーと安全なリンクルールの違いは明らかです。 **\*-SafeLinksPolicy** コマンドレットを使用して安全なリンクに関するポリシーを管理し、**\*-SafeLinksRule** コマンドレットを使用して安全なリンクに関するルールを管理します。

- PowerShell では、最初に安全なリンクに関するポリシーを作成し、それからルールが適用されるポリシーを特定する安全なリンクに関するルールを作成します。
- PowerShell では、安全なリンクに関するポリシーと安全なリンクに関するルールの設定は別々に変更します。
- PowerShell から安全なリンクに関するポリシーを削除しても、対応している安全なリンクに関するルールは自動で削除されず、逆もまた同様です。

### <a name="use-powershell-to-create-safe-links-policies"></a>PowerShell を使用して安全なリンク ポリシーを作成する

PowerShell では、以下の 2 段階の手順でマルウェア対策ポリシーを作成します。

1. 安全なリンクに関するポリシーを作成します。
2. ルールが適用される安全なリンク ポリシーを指定する安全なリンク規則を作成します。

> [!NOTE]
>
> - 新しい安全なリンクに関するルールを作成し、関連付けられていない既存の安全なリンクに関するポリシーをそれに割り当てることができます。 安全なリンクに関するルールを複数の安全なリンクに関するポリシーに関連付けることはできません。
>
> - ポリシーを作成するまで Microsoft 365 Defender ポータルで使用できない次の設定を、PowerShell で新しい安全なリンクに関するポリシーに構成できます。
>   - 新しいポリシーを無効として作成します (**New-SafeLinksRule コマンドレットで**_有効)。_ `$false`
>   - **New-SafeLinksRule** コマンドレットの作成時のポリシーの _優先度 (優先度__\<Number\>_) を設定します。
>
> - ポリシーを安全なリンクに関するルールに割り当てるまでは、PowerShell で作成した新しい安全なリンクに関するポリシーを Microsoft 365 Defender ポータルに表示することはできません。

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>手順 1: PowerShell を使用して安全なリンク ポリシーを作成する

安全なリンク ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSafeLinksForEmail <$true | $false>] [-EnableSafeLinksForOffice <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-AllowClickThrough <$true | $false>] [-TrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - _DoNotRewriteUrls_ パラメーターに使用するエントリ構文の詳細については、「[次の URL を書き換えない」の一覧のエントリ構文を参照してください](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。
>
> - **Set-SafeLinksPolicy** コマンドレットを使用して既存のセーフ リンク ポリシーを変更するときに _DoNotRewriteUrls_ パラメーターに使用できるその他の構文については、この記事の後半の [「PowerShell を使用して安全なリンク ポリシーを変更する](#use-powershell-to-modify-safe-links-policies)」セクションを参照してください。

この例では、Contoso All という名前の安全なリンク ポリシーを次の値で作成します。

- メール メッセージで URL スキャンと URL 書き換えを有効にします。
  - 内部メッセージの URL スキャンと書き換えを有効にします。
  - クリックされた URL のリアルタイム スキャン (ファイルを指すクリックされたリンクを含む) を有効にします。
    - URL スキャンが完了するまで待ち、その後でメッセージを配信します。
- Teams で URL スキャンを有効にします。
- サポートされている Office アプリで URL スキャンを有効にします。
- セーフ リンク保護に関連するユーザーのクリックを追跡します ( _TrackUserClicks_ パラメーターは使用されておらず、既定値は$true)。
- ユーザーが元の URL までクリックできないようにします。

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -EnableSafeLinksForEmail $true -EnableSafeLinksForOffice $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -AllowClickThrough $false
```

構文とパラメーターの詳細については、「 [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy)」を参照してください。

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>手順 2: PowerShell を使用して安全なリンク規則を作成する

安全なリンク規則を作成するには、次の構文を使用します。

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

この例では、Contoso All という名前の安全なリンク規則を次の条件で作成します。

- ルールは、Contoso All という名前の安全なリンクに関するポリシーに関連付けられています。
- contoso.com ドメイン内の受信者にルールを適用する。
- _Priority_ パラメーターを使用していないため、既定の優先度が使用されます。
- ルールは有効です ( _Enabled_ パラメーターは使用せず、既定値は `$true`有効です)。

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

この例では、前の例に似た安全なリンク規則を作成しますが、この例では、ルールは組織内のすべての承認済みドメインの受信者に適用されます。

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs (Get-AcceptedDomain).Name
```

この例では、前の例に似た安全なリンク規則を作成しますが、この例では、.csv ファイルで指定されたドメイン内の受信者にルールが適用されます。

```powershell
$Data = Import-Csv -Path "C:\Data\SafeLinksDomains.csv"
$SLDomains = $Data.Domains
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs $SLDomains
```

構文とパラメーターの詳細については、「 [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule)」を参照してください。

### <a name="use-powershell-to-view-safe-links-policies"></a>PowerShell を使用して安全なリンク ポリシーを表示する

既存の安全なリンク ポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全なリンク ポリシーの概要一覧を返します。

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

この例では、Contoso Executives という名前の安全なリンク ポリシーの詳細な情報を返します。

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

構文とパラメーターの詳細については、「 [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)」を参照してください。

### <a name="use-powershell-to-view-safe-links-rules"></a>PowerShell を使用して安全なリンクルールを表示する

既存の安全なリンク規則を表示するには、次の構文を使用します。

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

次の使用例は、すべての安全なリンク規則の概要リストを返します。

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

この例では、Contoso Executives という名前の安全なリンク規則の詳細な情報を返します。

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

構文とパラメーターの詳細については、「 [Get-SafeLinksRule」を](/powershell/module/exchange/get-safelinksrule)参照してください。

### <a name="use-powershell-to-modify-safe-links-policies"></a>PowerShell を使用して安全なリンク ポリシーを変更する

PowerShell で安全なリンク ポリシーの名前を変更することはできません ( **Set-SafeLinksPolicy** コマンドレットには _Name_ パラメーターがありません)。 Microsoft 365 Defender ポータルでセーフ リンク ポリシーの名前を変更すると、安全なリンク _ルール_ の名前のみが変更されます。

PowerShell で安全なリンク ポリシーを変更するための唯一の追加の考慮事項は、 _DoNotRewriteUrls_ パラメーター ( ["次の URL を書き換えない" リスト](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)) で使用できる構文です。

- 既存のエントリを置き換える値を追加するには、次の構文を使用します `"Entry1","Entry2,..."EntryN"`。
- 他の既存のエントリに影響を与えずに値を追加または削除するには、次の構文を使用します。 `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

それ以外の場合は、この記事の [「手順 1: PowerShell を使用して](#step-1-use-powershell-to-create-a-safe-links-policy) 安全なリンク ポリシーを作成する」セクションで説明したように、安全なリンク ポリシーを作成するときに、同じ設定を使用できます。

安全なリンク ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については、「 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)」を参照してください。

### <a name="use-powershell-to-modify-safe-links-rules"></a>PowerShell を使用して安全なリンク規則を変更する

PowerShell で安全なリンク規則を変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。 既存の安全なリンク規則を有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、この記事の「 [手順 2: PowerShell を使用して安全なリンク規則を作成する](#step-2-use-powershell-to-create-a-safe-links-rule) 」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。

安全なリンク規則を変更するには、次の構文を使用します。

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

この例では、Contoso All という名前の安全なリンク規則に、組織内のすべての承認済みドメインを条件として追加します。

```powershell
Set-SafeLinksRule -Identity "Contoso All" -RecipientDomainIs (Get-AcceptedDomain).Name
```

この例では、指定した.csvのドメインを条件として Contoso All という名前の安全なリンク規則に追加します。

```powershell
$Data = Import-Csv -Path "C:\Data\SafeLinksDomains.csv"
$SLDomains = $Data.Domains
Set-SafeLinksRule -Identity "Contoso All" -RecipientDomainIs $SLDomains
```

構文とパラメーターの詳細については、「 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)」を参照してください。

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>PowerShell を使用して安全なリンク規則を有効または無効にする

PowerShell で安全なリンク規則を有効または無効にすると、セーフ リンク ポリシー全体 (安全なリンク規則と割り当てられた安全なリンク ポリシー) 全体が有効または無効になります。

PowerShell で安全なリンク規則を有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

この例では、Marketing Department という名前の安全なリンク 規則を無効にします。

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「 [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) および [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule)」を参照してください。

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>PowerShell を使用して安全なリンクに関するルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell で安全なリンクに関するルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> 新しく作成したルールの優先度を設定するには、代わりに **New-MalwareFilterRule** コマンドレットの _Priority_ パラメーターを使用します。

構文とパラメーターの詳細については、「 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)」を参照してください。

### <a name="use-powershell-to-remove-safe-links-policies"></a>PowerShell を使用して安全なリンク ポリシーを削除する

PowerShell を使用して安全なリンク ポリシーを削除する場合、対応する安全なリンク規則は削除されません。

PowerShell で安全なリンク ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全なリンク ポリシーを削除します。

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「 [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy)」を参照してください。

### <a name="use-powershell-to-remove-safe-links-rules"></a>PowerShell を使用して安全なリンク規則を削除する

PowerShell を使用して安全なリンク規則を削除する場合、対応する安全なリンク ポリシーは削除されません。

PowerShell で安全なリンク規則を削除するには、次の構文を使用します。

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

次の使用例は、Marketing Department という名前の安全なリンク 規則を削除します。

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「 [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule)」を参照してください。

安全なリンクがメッセージをスキャンしていることを確認するには、使用可能なMicrosoft Defender for Office 365レポートを確認します。 詳細については、[Microsoft 365 Defender](view-reports-for-mdo.md) [ポータルでのDefender for Office 365およびエクスプローラーの使用に関するレポートの表示に関するMicrosoft 365 Defender](threat-explorer.md)を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

セーフ リンク ポリシーが正常に作成、変更、または削除されたことを確認するには、次のいずれかの手順を実行します。

- Microsoft 365 Defender ポータルの **[安全なリンク**] ページで<https://security.microsoft.com/safelinksv2>、ポリシーの一覧、**状態** の値、および **優先度** の値を確認します。 詳細を表示するには、一覧からポリシーを選択し、ポップアップで詳細を表示します。

- PowerShell または powerShell Exchange Online Protection Exchange Onlineで、ポリシーまたはルールの名前に置き換え\<Name\>、次のコマンドを実行し、設定を確認します。

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
