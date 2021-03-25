---
title: スプーフィング インテリジェンスを構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、特定のスプーフィング送信者を許可またはブロックできる Exchange Online Protection (EOP) でスプーフィング インテリジェンスについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c13c080829236b9a27b6a1a82e1c27256749b5c2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205463"
---
# <a name="configure-spoof-intelligence-in-eop"></a>EOP でスプーフィング インテリジェンスを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online メールボックスのない Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織のメールボックスを持つ Microsoft 365 組織では、受信電子メール メッセージは 2018 年 10 月現在、EOP によるスプーフィングから自動的に保護されます。 EOP は、フィッシングに対する組織の全体的な防御の一環としてスプーフィング インテリジェンスを使用します。 詳細については、「EOP でのスプーフィング防止 [保護」を参照してください](anti-spoofing-protection.md)。

送信者が電子メール アドレスをスプーフィングすると、その送信者は組織のドメインの 1 つのユーザー、または組織に電子メールを送信する外部ドメインのユーザーのように見える。 送信者をスプーフィングしてスパムメールやフィッシングメールを送信する攻撃者をブロックする必要があります。 しかし、正当な送信者がスプーフィングを行うシナリオがあります。 以下に例を示します。

- 内部ドメインをスプーフィングする正当なシナリオ:

  - サードパーティの送信者は、ドメインを使用して、会社の投票のために自分の従業員にバルク メールを送信します。
  - 外部企業は、お客様に代わって広告や製品の更新プログラムを生成して送信します。
  - アシスタントは、組織内の別のユーザーのメールを定期的に送信する必要があります。
  - 内部アプリケーションが電子メール通知を送信します。

- 外部ドメインをスプーフィングする正当なシナリオ:

  - 送信者はメーリングリスト (ディスカッション リストとも呼ばれる) に登録され、メーリングリストは元の送信者からメーリングリストのすべての参加者にメールを中継します。
  - 外部企業は、別の会社に代わって電子メールを送信します (たとえば、自動レポートやサービスとしてのソフトウェア会社など)。

スプーフィング インテリジェンス(特に既定のスプーフィング インテリジェンス ポリシー)は、正当な送信者から送信されるスプーフィングされたメールが EOP スパム フィルターや外部メール システムに巻き込まれたり、スパムやフィッシング攻撃からユーザーを保護したりすることを防ごうのに役立ちます。

スプーフィング インテリジェンスは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で管理できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。 フィッシング対策ページに直接 **移動するには** 、 を使用します <https://protection.office.com/antiphishing> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - スプーフィング インテリジェンス ポリシーを変更したり、スプーフィング インテリジェンスを有効または無効にするには、組織の管理またはセキュリティ管理者の役割グループのメンバー **である** 必要があります。
  - スプーフィング インテリジェンス ポリシーへの読み取り専用アクセスでは、グローバルリーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- スプーフィング インテリジェンスの推奨設定については [、「EOP の既定のフィッシング対策ポリシー設定」を参照してください](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)。

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>セキュリティ コンプライアンス センター&を使用して、スプーフィングされた送信者を管理する

> [!NOTE]
> Microsoft 365 Enterprise E5 サブスクリプションを持っている場合、または Office 365 アドオン用の Microsoft Defender を個別に購入している場合は、スプーフィング インテリジェンス[](walkthrough-spoof-intelligence-insight.md)の分析情報を使用してドメインをスプーフィングしている送信者を管理できます。

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム対策 **の設定] ページで、[** 展開] アイコン ![ をクリックして [ス ](../../media/scc-expand-icon.png) プーフィング インテリジェンス ポリシー **] を展開します**。

   ![スプーフィング インテリジェンス ポリシーの選択](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. 次のいずれかの選択を行います。

   - **新しい送信者を確認する**
   - **既に確認した送信者を表示する**

4. [表示 **されるユーザーのスプー** フィングを許可する送信者を決定する] フライアウトで、次のいずれかのタブを選択します。

   - **[ドメイン]:** 内部ドメイン内のユーザーをスプーフィングする送信者。
   - **外部ドメイン**: 外部ドメイン内のユーザーをスプーフィングする送信者。

5. [ス ![ プーフィングを ](../../media/scc-expand-icon.png) 許可する] **列の [展開] アイコンをクリック** します。 ス **プーフィング** された送信者を許可するには [はい] を選択し、メッセージをスプーフィングとしてマークするには **[いいえ** ] を選択します。 アクションは、既定のフィッシング対策ポリシーまたはカスタムのフィッシング対策ポリシーによって制御されます (既定値は [メッセージを迷惑メール フォルダーに移動する] **です**)。 詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。

   ![スプーフィングされた送信者の飛び出し、送信者がスプーフィングを許可されているかどうかを示すスクリーンショット](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   表示される列と値については、次の一覧で説明します。

   - **スプーフィング** されたユーザー: スプーフィングされているユーザー アカウント。 これは、メール クライアントに表示される差出人アドレス (アドレスとも呼ばれる) のメッセージ `5322.From` 送信者です。 このアドレスの有効性は SPF によってチェックされません。

     - [ドメイン **] タブ** で、値に 1 つの電子メール アドレスが含まれているか、送信元メール サーバーが複数のユーザー アカウントをスプーフィングしている場合は、複数のユーザー アカウントが **含まれる。**

     - [外部 **ドメイン] タブ** の値には、完全なメール アドレスではなく、スプーフィングされたユーザーのドメインが含まれる。

   - **送信インフラストラクチャ**: 送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン。 送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは \<source IP\> /24 として識別されます (たとえば、192.168.100.100/24 など)。

     メッセージ ソースとメッセージ送信者の詳細については、「電子メール メッセージ標準の概要 [」を参照してください](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

   - **メッセージ数**: 過去 30 日以内に、指定されたスプーフィングされた送信者または送信者を含む、送信側インフラストラクチャから組織へのメッセージの数。

   - **ユーザーからの苦情の** 数 : 過去 30 日以内にこの送信者に対してユーザーが申し立てした苦情。 苦情は通常、Microsoft への迷惑メール申請の形式です。

   - **認証結果**: 次のいずれかの値を指定します。
      - **合格**: 送信者が送信者の電子メール認証チェック (SPF または DKIM) を渡しました。
      - **Failed**: 送信者が EOP 送信者認証のチェックに失敗しました。
      - **不明**: これらのチェックの結果は不明です。

   - **決定セット :** 送信インフラストラクチャがユーザーのスプーフィングを許可されるユーザーを示します。
       - **スプーフィング インテリジェンス ポリシー** (自動)
       - **管理者** (手動)

   - **最後に** 表示される : スプーフィングされたユーザーを含む送信インフラストラクチャからメッセージを受信した最後の日付。

   - **スプーフィングを許可しますか。**: ここに表示される値は次のとおりです。
     - **は** い : スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは許可され、スプーフィングされた電子メールとして扱われるのではありません。
     - **いいえ**: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。 アクションは、既定のフィッシング対策ポリシーまたはカスタムのフィッシング対策ポリシーによって制御されます (既定値は [メッセージを迷惑メール フォルダーに移動する] **です**)。 詳細については、次のセクションを参照してください。

     - **一部** のユーザー (**[ドメイン** ] タブのみ): 送信インフラストラクチャは複数のユーザーをスプーフィングしています。スプーフィングされたユーザーの中には許可されているユーザーと許可されていないユーザーがあります。 [詳細] **タブを使用** して、特定のアドレスを表示します。

6. ページの下部にある [**保存**] をクリックします。

## <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell を使用してスプーフィングされた送信者を管理する

スプーフィング インテリジェンスで許可送信者とブロック送信者を表示するには、次の構文を使用します。

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

この例では、ドメイン内のユーザーをスプーフィングできるすべての送信者に関する詳細情報を返します。

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

構文とパラメーターの詳細については [、「Get-PhishFilterPolicy」を参照してください](/powershell/module/exchange/get-phishfilterpolicy)。

スプーフィング インテリジェンスで許可送信者とブロック送信者を構成するには、次の手順を実行します。

1. **Get-PhishFilterPolicy** コマンドレットの出力を CSV ファイルに書き込み、検出されたスプーフィングされた送信者の現在のリストをキャプチャします。

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. CSV ファイルを編集して、スプーフィング **ユーザー** (電子メール アドレス) と **AllowedToSpoof (Yes** または No) の値を追加または変更します。 ファイルを保存し、ファイルを読み取り、内容を次の名前の変数として格納します `$UpdateSpoofedSenders` 。

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 変数を `$UpdateSpoofedSenders` 使用してスプーフィング インテリジェンス ポリシーを構成します。

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

構文とパラメーターの詳細については [、「Set-PhishFilterPolicy」を参照してください](/powershell/module/exchange/set-phishfilterpolicy)。

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>コンプライアンス センターのセキュリティ &を使用してスプーフィング インテリジェンスを構成する

スプーフィング インテリジェンスの構成オプションについては、「フィッシング対策ポリシーのスプーフィング [設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。

スプーフィング インテリジェンス設定は、既定のフィッシング対策ポリシーとカスタム ポリシーで構成できます。 サブスクリプションに基づく手順については、次のいずれかのトピックを参照してください。

- [EOP でフィッシング対策ポリシーを構成します](configure-anti-phishing-policies-eop.md)。

- [Microsoft Defender でフィッシング対策ポリシーを構成して、Office 365 に設定します](configure-atp-anti-phishing-policies.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

スプーフィングが許可され、許可されていない送信者とスプーフィング インテリジェンスを構成し、スプーフィング インテリジェンス設定が構成されていることを確認するには、次の手順を実行します。

- セキュリティ & コンプライアンス センターで、[脅威管理ポリシースパム対策] [スプーフィング インテリジェンス ポリシー] の [送信者を表示する] を選択し、[ドメインまたは外部ドメイン] タブを選択し、送信者の [スプーフィングを許可する \>  \>  \>  \>  \> **]** 値を確認します。

- PowerShell で、次のコマンドを実行して、スプーフィングが許可されている送信者とスプーフィングが許可されていない送信者を表示します。

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- PowerShell で、次のコマンドを実行して、すべてのスプーフィングされた送信者の一覧を CSV ファイルにエクスポートします。

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- [セキュリティ & コンプライアンス センター] で、[脅威管理ポリシー] [フィッシング対策] または [ATP フィッシング対策] に移動し、次のいずれかの手順 \>  \> を実行します。   

  - 一覧からポリシーを選択します。 表示されるフライアウトで、[スプーフィング] セクションの値を **確認** します。
  - [既定 **のポリシー] をクリックします**。 表示されるフライアウトで、[スプーフィング] セクションの値を **確認** します。

- Exchange Online PowerShell で、Office365 AntiPhish Default またはカスタム ポリシーの名前に置き換え、次のコマンドを実行して設定 \<Name\> を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>スプーフィングとフィッシングを管理するその他の方法

スプーフィングとフィッシング保護について詳しく知る。 ドメインをスプーフィングする送信者を確認し、組織に損害を与えないよう、関連する方法を次に示します。

- スプーフィン **グ メール レポートを確認します**。 このレポートを頻繁に使用して、スプーフィングされた送信者を表示および管理できます。 詳細については、「スプーフィング [検出レポート」を参照してください](view-email-security-reports.md#spoof-detections-report)。

- 送信者ポリシー フレームワーク (SPF) 構成を確認します。 SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。 Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。

- DomainKeys Identified Mail (DKIM) 構成を確認します。 SPF と DMARC に加えて DKIM を使用して、攻撃者が自分のドメインから送信されたようなメッセージを送信するのを防ぐ必要があります。 DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。 詳細については [、「Use DKIM to validate outbound email](use-dkim-to-validate-outbound-email.md)from your custom domain in your custom domain in Office 365 .

- ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC) 構成を確認します。 SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。 DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。 詳細については [、「Use DMARC to validate email in Office 365」を参照してください](use-dmarc-to-validate-email.md)。