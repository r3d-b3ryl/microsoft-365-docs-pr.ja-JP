---
title: スプーフィング インテリジェンス ポリシーとスプーフィング インテリジェンス 分析情報を使用してスプーフィングされた送信者を管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 管理者は、スプーフィング インテリジェンス ポリシーとスプーフィング インテリジェンス分析情報を使用して、検出されたスプーフィングされた送信者を許可またはブロックする方法を学習できます。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 59f52e7fe10030283601aad86a1aa49ed91255ab
ms.sourcegitcommit: 363bdc517bd2564c6420cf21f352e97079f950e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031825"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a>EOP でスプーフィング インテリジェンス ポリシーとスプーフィング インテリジェンス 分析情報を使用してスプーフィングされた送信者を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事では、置き換えられる以前のスプーフィング送信者管理エクスペリエンス (**スパム対策ポリシー** ページの **スプーフィング インテリジェンス ポリシー**) について説明します。 新しいエクスペリエンス (テナント許可/ブロック リストの **[スプーフィング** ] タブ) の詳細については、 [EOP のスプーフィング インテリジェンス分析情報に](learn-about-spoof-intelligence.md)関するページを参照してください。

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを持つMicrosoft 365組織では、Exchange Onlineメールボックスがない場合、受信電子メール メッセージは 2018 年 10 月の時点で EOP によるスプーフィングから自動的に保護されます。 EOP では、フィッシングに対する組織全体の防御の一環として **、スプーフィング インテリジェンス** が使用されます。 詳細については、「 [EOP でのスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。

既定の (および唯一の) **スプーフィング インテリジェンス ポリシー** は、正当な送信者によって送信されたスプーフィングされた電子メールが EOP スパム フィルターに巻き込まれないようにするのに役立ち、ユーザーをスパムまたはフィッシング攻撃から保護します。 **スプーフィング インテリジェンス分析情報** を使用して、認証されていないメール (SPF、DKIM、DMARC チェックに合格しないドメインからのメッセージ) を正当に送信している外部送信者をすばやく特定することもできます。

スプーフィング インテリジェンスは、Microsoft 365 Defender ポータルまたは PowerShell (Exchange Online のメールボックスを持つMicrosoft 365組織の PowerShell をExchange Online)、Exchange Onlineのない組織向けのスタンドアロン EOP PowerShell で管理できます。 メールボックス)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - スプーフィング インテリジェンス ポリシーを変更したり、スプーフィング インテリジェンスを有効または無効にするには、 
    -   **組織の管理**
    -   **セキュリティ管理者**<u>と</u>**表示専用構成** または **表示専用組織管理**。
  - スプーフィング インテリジェンス ポリシーへの読み取り専用アクセスの場合は、 **グローバル リーダー** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- スプーフィング インテリジェンスのオプションについては、「 [フィッシング対策ポリシーのスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。

- フィッシング対策ポリシーでは、スプーフィング インテリジェンス設定を有効、無効、および構成できます。 サブスクリプションに基づく手順については、次のいずれかのトピックを参照してください。

  - [EOP でフィッシング対策ポリシーを構成します](configure-anti-phishing-policies-eop.md)。
  - [Microsoft Defender for Office 365でフィッシング対策ポリシーを構成](configure-mdo-anti-phishing-policies.md)します。

- スプーフィング インテリジェンスの推奨設定については、「 [EOP フィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)」を参照してください。

## <a name="manage-spoofed-senders"></a>スプーフィングされた送信者を管理する

スプーフィングされた送信者を許可およびブロックするには、次の 2 つの方法があります。

- [スプーフィング インテリジェンス ポリシーを使用する](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [スプーフィング インテリジェンスの分析情報を使用する](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a>スプーフィング インテリジェンス ポリシーでスプーフィングされた送信者を管理する

> [!IMPORTANT]
> この記事では、置き換えられる以前のスプーフィング送信者管理エクスペリエンス (**スパム対策ポリシー** ページの **スプーフィング インテリジェンス ポリシー**) について説明します。 新しいエクスペリエンス (テナント許可/ブロック リストの **[スプーフィング** ] タブ) の詳細については、 [EOP のスプーフィング インテリジェンス分析情報に](learn-about-spoof-intelligence.md)関するページを参照してください。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. [ **スパム対策ポリシー** ] ページで、名前をクリックして [ **スプーフィング インテリジェンス ポリシー** ] を選択します。

   :::image type="content" source="../../media/anti-spam-settings-spoof-intelligence-policy.png" alt-text="スプーフィング インテリジェンス ポリシーを選択するオプション" lightbox="../../media/anti-spam-settings-spoof-intelligence-policy.png":::

3. 表示される **スプーフィング インテリジェンス ポリシー** ポップアップで、次のいずれかの選択を行います。
   - **既に確認した送信者を表示する**
   - **新しい送信者を確認する**

4. [ **これらの送信者が表示されるユーザーのポップアップをスプーフィングすることを許可するかどうかを決定** する] で、次のいずれかのタブを選択します。
   - **ドメイン**: 送信者が内部ドメイン内のユーザーをスプーフィングします。
   - **外部ドメイン**: 送信者が外部ドメインのユーザーをスプーフィングしています。

5. [展開] アイコンをクリック ![します。](../../media/scc-expand-icon.png) [ **スプーフィングが許可されていますか?** ] 列で、次のいずれかの選択を行います。
   - **はい**: スプーフィングされた送信者を許可します。
   - **いいえ**: メッセージをスプーフィングとしてマークします。 アクションは、既定のフィッシング対策ポリシーまたはカスタムフィッシング対策ポリシーによって制御されます。 詳細については、「[フィッシング詐欺対策ポリシーでのなりすまし設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。

   :::image type="content" source="../../media/spoof-allow-block-flyout.png" alt-text="スプーフィングされた送信者のポップアップと、送信者がスプーフィングを許可されているかどうか" lightbox="../../media/spoof-allow-block-flyout.png":::

   表示される列と値については、次の一覧で説明します。

   - **スプーフィングされたユーザー**: スプーフィングされているユーザー アカウント。 これは、電子メール クライアントに表示される差出人アドレス (アドレスとも呼ばれます `5322.From` ) のメッセージ送信者です。 このアドレスの有効性は SPF によってチェックされません。
     - [ **ドメイン** ] タブで、値に 1 つのメール アドレスが含まれているか、ソース電子メール サーバーが複数のユーザー アカウントをスプーフィングしている場合は、 **複数** のユーザー アカウントが含まれます。
     - [ **外部ドメイン** ] タブの値には、完全な電子メール アドレスではなく、スプーフィングされたユーザーのドメインが含まれます。

   - **送信インフラストラクチャ**: 送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン。 送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは /24 (たとえば、192.168.100.100/24) として \<source IP\>識別されます。

     メッセージ ソースとメッセージ送信者の詳細については、「 [電子メール メッセージ標準の概要](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)」を参照してください。

   - **メッセージの数**: 過去 30 日以内に指定されたスプーフィングされた送信者または送信者を含む、組織への送信インフラストラクチャからのメッセージの数。

   - **#of user complaints**: 過去 30 日以内にこの送信者に対してユーザーが提出した苦情。 苦情は通常、Microsoft に迷惑メールを送信する形式です。

   - **認証結果**: 次のいずれかの値。
      - **成功**: 送信者が送信者の電子メール認証チェック (SPF または DKIM) に合格しました。
      - **失敗:** 送信者が EOP 送信者認証チェックに失敗しました。
      - **不明**: これらのチェックの結果は不明です。

   - **最終更新日**: スプーフィングされたユーザーを含む送信インフラストラクチャからメッセージを受信した最後の日付。

   - **スプーフィングが許可されていますか?**: ここに表示される値は次のとおりです。
     - **はい**: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは許可され、スプーフィングされた電子メールとして扱われません。
     - **いいえ**: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。 アクションは、既定のフィッシング対策ポリシーまたはカスタムフィッシング対策ポリシー (既定値は迷惑 **メール フォルダーにメッセージを移動**) によって制御されます。 詳細については、次のセクションを参照してください。

     - **一部のユーザー** (**[ドメイン** ] タブのみ): 送信インフラストラクチャは複数のユーザーをスプーフィングしています。一部のスプーフィングされたユーザーは許可され、他のユーザーは許可されません。 [ **詳細** ] タブを使用して、特定のアドレスを表示します。

6. 完了したら、**[保存]** をクリックします。

#### <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell を使用してスプーフィングされた送信者を管理する

> [!IMPORTANT]
> この記事では、置き換えられる以前のスプーフィング送信者管理エクスペリエンス (**スパム対策ポリシー** ページの **スプーフィング インテリジェンス ポリシー**) について説明します。 新しいエクスペリエンス (テナント許可/ブロック リストの **[スプーフィング** ] タブ) の詳細については、 [EOP のスプーフィング インテリジェンス分析情報に](learn-about-spoof-intelligence.md)関するページを参照してください。

許可された送信者とブロックされた送信者をスプーフィング インテリジェンスで表示するには、次の構文を使用します。

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

この例では、ドメイン内のユーザーのスプーフィングが許可されているすべての送信者に関する詳細情報を返します。

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

構文とパラメーターの詳細については、「 [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy)」を参照してください。

スプーフィング インテリジェンスで許可およびブロックされた送信者を構成するには、次の手順に従います。

1. **Get-PhishFilterPolicy** コマンドレットの出力を CSV ファイルに書き込み、次のコマンドを実行して、検出されたスプーフィングされた送信者の現在の一覧をキャプチャします。

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. CSV ファイルを編集して、次の値を追加または変更します。
   - **送信者** (ソース サーバーの PTR レコードまたは IP/24 アドレスのドメイン)
   - **スプーフィングユーザー**: 次のいずれかの値。
     - 内部ユーザーの電子メール アドレス。
     - 外部ユーザーの電子メール ドメイン。
     - スプーフィングされた電子メール アドレスに関係なく、指定した **送信者** からのスプーフィングされたメッセージをブロックまたは許可することを示す空白の値。
   - **AllowedToSpoof** (はいまたはいいえ)
   - **SpoofType** (内部または外部)

   次のコマンドを実行して、ファイルを保存し、ファイルを読み取り、内容を名前付きの `$UpdateSpoofedSenders` 変数として格納します。

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 次のコマンドを `$UpdateSpoofedSenders` 実行して、変数を使用してスプーフィング インテリジェンス ポリシーを構成します。

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

構文とパラメーターの詳細については、「 [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy)」を参照してください。

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a>スプーフィング インテリジェンス分析情報でスプーフィングされた送信者を管理する

> [!IMPORTANT]
> この記事では、置き換えられる以前のスプーフィング送信者管理エクスペリエンス (**スパム対策ポリシー** ページの **スプーフィング インテリジェンス ポリシー**) について説明します。 新しいエクスペリエンス (テナント許可/ブロック リストの **[スプーフィング** ] タブ) の詳細については、 [EOP のスプーフィング インテリジェンス分析情報に](learn-about-spoof-intelligence.md)関するページを参照してください。

1. セキュリティ & コンプライアンス センターで、**脅威管理**\>ダッシュボードに移動 **します**。

2. **インサイト** 行で、次のいずれかの項目を探します。

   - **過去 7 日間にスプーフィングされた可能性のあるドメイン**: この分析情報は、スプーフィング インテリジェンスが有効になっていることを示します (既定で有効になっています)。
   - **スプーフィング保護を有効にする**: この分析情報は、スプーフィング インテリジェンスが無効になっていることを示し、分析情報をクリックするとスプーフィング インテリジェンスを有効にすることができます。

3. ダッシュボードの分析情報には、次のような情報が表示されます。

   :::image type="content" source="../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png" alt-text="スプーフィング インテリジェンスの分析情報" lightbox="../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png":::

   この分析情報には、次の 2 つのモードがあります。

   - **分析情報モード**: スプーフィング インテリジェンスが有効になっている場合、過去 7 日間にスプーフィング インテリジェンス機能によって影響を受けたメッセージの数が分析情報に表示されます。
   - **What if mode**: スプーフィング インテリジェンスが無効になっている場合、過去 7 日間にスプーフィング インテリジェンス機能によって影響を受 *けたメッセージの* 数が分析情報に表示されます。

   どちらの方法でも、分析情報に表示されるスプーフィングされたドメインは、 **疑わしいドメイン** と **疑わしいドメイン** の 2 つのカテゴリに分けられます。

   - **疑わしいドメイン**:
     - **高信頼スプーフィング**: 過去の送信パターンとドメインの評判スコアに基づいて、ドメインがスプーフィングされ、これらのドメインからのメッセージが悪意を持つ可能性が高いことを確信しています。
     - **中程度の信頼スプーフィング**: 過去の送信パターンとドメインの評判スコアに基づいて、ドメインがスプーフィングされ、これらのドメインから送信されたメッセージが正当であると確信しています。 このカテゴリでは、信頼度の高いスプーフィングよりも誤検知の可能性が高くなります。
   - **非疑わしいドメイン**: ドメインで、[SPF、](how-office-365-uses-spf-to-prevent-spoofing.md)[DKIM](use-dkim-to-validate-outbound-email.md)、[および DMARC](use-dmarc-to-validate-email.md) の明示的な電子メール認証チェックに失敗しました。 ただし、ドメインは暗黙的な電子メール認証チェック ([複合認証](email-validation-and-authentication.md#composite-authentication)) に合格しました。 その結果、メッセージに対してスプーフィング対策アクションは実行されませんでした。

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a>疑わしいドメインと疑わしいドメインに関する詳細情報を表示する

1. スプーフィング インテリジェンス分析情報で、[ **不審なドメイン** ] または **[疑わしいドメイン以外のドメイン** ] をクリックして、[ **スプーフィング インテリジェンスの分析情報]** ページに移動します。 **スプーフィング インテリジェンス分析情報** ページには、次の情報が含まれています。

   - **スプーフィングされたドメイン**: メール クライアントの [ **送信元** ] ボックスに表示されるスプーフィングされたユーザーのドメイン。 このアドレスは、アドレスとも `5322.From` 呼ばれます。
   - **インフラストラクチャ**: _送信インフラストラクチャ_ とも呼ばれます。 送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン。 送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは /24 (たとえば、192.168.100.100/24) として \<source IP\>識別されます。
   - **メッセージ数**: 過去 7 日以内に指定されたスプーフィングされたドメインを含む組織への送信インフラストラクチャからのメッセージの数。
   - **最終更新日**: スプーフィングされたドメインを含む送信インフラストラクチャからメッセージを受信した最後の日付。
   - **スプーフィングの種類**: この値は **外部** です。
   - **スプーフィングが許可されていますか?**: ここに表示される値は次のとおりです。
     - **はい**: スプーフィングされたユーザーのドメインと送信インフラストラクチャの組み合わせからのメッセージは許可され、スプーフィングされた電子メールとして扱われません。
     - **いいえ**: スプーフィングされたユーザーのドメインと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。 アクションは、既定のフィッシング対策ポリシーまたはカスタムフィッシング対策ポリシー (既定値は迷惑 **メール フォルダーにメッセージを移動**) によって制御されます。

2. 一覧で項目を選択すると、ポップアップでドメインと送信インフラストラクチャのペアに関する詳細が表示されます。 情報には次のものが含まれます。
   - これをキャッチした理由。
   - 実行する必要がある操作。
   - ドメインの概要。
   - 送信者に関する WhoIs データ。
   - 同じ送信者からテナントで見た同様のメッセージ。

   ここから、ドメインと送信インフラストラクチャのペアを[ **許可されたスプーフィング** 送信者許可] ボックスの一覧から追加または削除することもできます。 それに応じてトグルを設定するだけです。

   :::image type="content" source="../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png" alt-text="スプーフィング インテリジェンス分析情報の詳細ウィンドウのドメイン" lightbox="../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png":::

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

スプーフィングが許可され、スプーフィングが許可されていない送信者でスプーフィング インテリジェンスを構成したことを確認するには、次のいずれかの手順を使用します。

- **電子メール & コラボレーション** \>**ポリシー&ルール** \>**脅威ポリシー** \>**[ポリシー**] セクションの **[スパム対策**] で \> [**スプーフィング インテリジェンス ポリシー**\>] を選択し、[**自分**\>の **ドメイン** または **外部ドメイン**] タブを選択し、送信者の [**スプーフィングが許可されていますか?** ] の値を確認します。

- PowerShell で、次のコマンドを実行して、スプーフィングが許可され、スプーフィングが許可されていない送信者を表示します。

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- PowerShell で、次のコマンドを実行して、スプーフィングされたすべての送信者の一覧を CSV ファイルにエクスポートします。

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
