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
description: 管理者は、特定のスプーフィングされた送信者を許可またはブロックできる Exchange Online Protection (EOP) のスプーフィング インテリジェンスについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a65400d1b48abfc6ac0e4dd38a8245dd7b4f87b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289689"
---
# <a name="configure-spoof-intelligence-in-eop"></a>EOP でスプーフィング インテリジェンスを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、受信電子メール メッセージは 2018 年 10 月の現在、EOP によるスプーフィングから自動的に保護されます。 EOP は、フィッシングに対する組織の全体的な防御の一部としてスプーフィング インテリジェンスを使用します。 詳細については [、「EOP でのスプーフィング対策保護」を参照してください](anti-spoofing-protection.md)。

送信者がメール アドレスをスプーフィングすると、その送信者は組織のドメインの 1 つのユーザー、または組織に電子メールを送信する外部ドメイン内のユーザーのように見える。 送信者を偽装してスパムやフィッシングメールを送信する攻撃者をブロックする必要があります。 ただし、正当な送信者がスプーフィングを行っているシナリオがあります。 例:

- 内部ドメインをスプーフィングする正当なシナリオ:

  - サード パーティの送信者は、ドメインを使用して、会社の投票のために自分の従業員にバルク メールを送信します。
  - 外部の会社が広告や製品の更新プログラムを生成し、ユーザーに代わって送信します。
  - アシスタントは、組織内の別のユーザーに電子メールを定期的に送信する必要があります。
  - 内部アプリケーションが電子メール通知を送信します。

- 外部ドメインをスプーフィングする正当なシナリオ:

  - 送信者がメール リスト (ディスカッション リストとも呼ばれる) に登録され、そのメール リストは元の送信者からそのメール リストのすべての参加者に電子メールを中継します。
  - 外部企業は、別の会社の代わりにメールを送信します (たとえば、自動レポートやサービスとしてのソフトウェア会社など)。

スプーフィング インテリジェンス、特に既定 (かつ唯一の) スプーフィング インテリジェンス ポリシーは、正当な送信者から送信されたスプーフィングされた電子メールが、スパムやフィッシング攻撃からユーザーを保護しながら、EOP スパム フィルターや外部の電子メール システムに巻き込まなかったりすることを防ごうのに役立ちます。

スプーフィング インテリジェンスは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを使用する Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で管理できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。 フィッシング対策ページに直接 **移動するには、次** のコマンドを使用します <https://protection.office.com/antiphishing> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。
  - スプーフィング インテリジェンス ポリシーを変更したり、スプーフィング インテリジェンスを有効または無効にするには、 **組織** の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。
  - スプーフィング インテリジェンス ポリシーに読み取り専用でアクセスするには、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である** 必要があります。

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- スプーフィング インテリジェンスの推奨設定については、「EOP の既定のフィッシング対策 [ポリシー設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>セキュリティ/コンプライアンス センター&使用して、スプーフィングされた送信者を管理する

> [!NOTE]
> Microsoft 365 Enterprise E5 サブスクリプションを持っている場合、または microsoft Defender for Office 365 アドオンを別途購入している場合は、スプーフィング インテリジェンスの洞察を通じてドメインをスプーフィングしている送信者を管理[できます。](walkthrough-spoof-intelligence-insight.md)

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム対策 **の設定] ページで、[** 展開] アイコンをクリック ![ ](../../media/scc-expand-icon.png) して、スプーフィング インテリジェンス **ポリシーを展開します**。

   ![スプーフィング インテリジェンス ポリシーを選択する](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. 次のいずれかを選択します。

   - **新しい送信者を確認する**
   - **既に確認した送信者を表示する**

4. 表示される **ユーザーのフライアウト** を、これらの送信者にスプーフィングを許可するか決定するで、次のいずれかのタブを選択します。

   - **ドメイン :** 内部ドメイン内のユーザーをスプーフィングする送信者。
   - **外部ドメイン**: 外部ドメイン内のユーザーをスプーフィングする送信者。

5. [ス ![ プーフィングの ](../../media/scc-expand-icon.png) 許可] 列の [展開] **アイコンをクリック** します。 ス **プーフィン** グされた送信者を許可するには [はい] を選択し、メッセージをスプーフィング済みとしてマークするには [ **いいえ** ] を選択します。 アクションは、既定のフィッシング対策ポリシーまたはカスタムのフィッシング対策ポリシー (既定値は [メッセージを迷惑メール フォルダーに移動] です) **によって制御されます**。 詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。

   ![スプーフィングされた送信者のフライアウトと、送信者がスプーフィングを許可されているかどうかを示すスクリーンショット](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   表示される列と値について、次の一覧で説明します。

   - **スプーフィング** されたユーザー: スプーフィングされているユーザー アカウント。 これは、電子メール クライアントに表示される差出人アドレス (アドレスとも呼ばれる) の `5322.From` メッセージ送信者です。 このアドレスの有効性は SPF によってチェックされません。

     - On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.

     - [ **外部ドメイン] タブ** の値には、完全な電子メール アドレスではなく、スプーフィングされたユーザーのドメインが含まれる。

   - **送信インフラストラクチャ**: 送信元の電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン。 送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは \<source IP\> /24 として識別されます (例: 192.168.100.100/24)。

     メッセージ ソースとメッセージ送信者の詳細については、「電子メール メッセージの標準の概要 [」を参照してください](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

   - **メッセージ数**: 過去 30 日以内に、指定されたスプーフィングされた送信者または送信者を含む、送信側インフラストラクチャから組織へのメッセージの数。

   - **# of user complaints**: Complaints filed by your users against this sender within the last 30 days. 苦情は通常、Microsoft への迷惑メール送信の形式です。

   - **認証結果**: 次のいずれかの値です。
      - **Passed**: 送信者が送信者の電子メール認証チェック (SPF または DKIM) に合格しました。
      - **Failed**: 送信者が EOP 送信者認証チェックに失敗しました。
      - **不明**: これらのチェックの結果が不明です。

   - **Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:
       - **スプーフィング インテリジェンス ポリシー** (自動)
       - **管理者** (手動)

   - **Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.

   - **スプーフィングが許可されますか?**: ここに表示される値は次のとおりです。
     - **は** い : スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは許可され、スプーフィングされた電子メールとして扱われるのではありません。
     - **いいえ**: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。 アクションは、既定のフィッシング対策ポリシーまたはカスタムのフィッシング対策ポリシー (既定値は [メッセージを迷惑メール フォルダーに移動] です) **によって制御されます**。 詳細については、次のセクションを参照してください。

     - **一部の** ユーザー **([自分** のドメイン] タブのみ): 送信インフラストラクチャは、複数のユーザーをスプーフィングします。スプーフィングされたユーザーが許可され、他のユーザーは許可されません。 [詳細 **] タブを使用** して、特定のアドレスを表示します。

6. ページの下部にある [**保存**] をクリックします。

## <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell を使用してスプーフィングされた送信者を管理する

スプーフィング インテリジェンスで許可された送信者とブロックする送信者を表示するには、次の構文を使用します。

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

この例では、ドメイン内のユーザーをスプーフィングできるすべての送信者に関する詳細情報を返します。

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

構文およびパラメーターの詳細については [、「Get-PhishFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)。

スプーフィング インテリジェンスで許可された送信者とブロックする送信者を構成するには、次の手順を実行します。

1. **Get-PhishFilterPolicy** コマンドレットの出力を CSV ファイルに書き込み、検出されたスプーフィングされた送信者の現在のリストをキャプチャします。

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. CSV ファイルを編集して **、SpoofedUser** (メール アドレス) と **AllowedToSpoof** (Yes または No) の値を追加または変更します。 ファイルを保存し、ファイルを読み取り、内容を次の名前の変数として保存します `$UpdateSpoofedSenders` 。

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 変数を `$UpdateSpoofedSenders` 使用して、スプーフィング インテリジェンス ポリシーを構成します。

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

構文およびパラメーターの詳細については [、「Set-PhishFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)。

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>セキュリティ/コンプライアンス センター&使用してスプーフィング インテリジェンスを構成する

スプーフィング インテリジェンスの構成オプションについては、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。

スプーフィング インテリジェンス設定は、既定のフィッシング対策ポリシーとカスタム ポリシーで構成できます。 サブスクリプションに基づく手順については、次のいずれかのトピックを参照してください。

- [EOP でフィッシング対策ポリシーを構成します](configure-anti-phishing-policies-eop.md)。

- [Microsoft Defender でフィッシング対策ポリシーを Office 365 用に構成します](configure-atp-anti-phishing-policies.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

スプーフィングが許可され、許可されていない送信者にスプーフィング インテリジェンスが構成済みであり、スプーフィング インテリジェンス設定が構成されていることを確認するには、次の手順を使用します。

- セキュリティ & コンプライアンス センターで、[脅威管理ポリシーのスパム対策] の [スプーフィング インテリジェンス] ポリシーに移動します。[既に確認した送信者を表示する] を選択し、[自分のドメインまたは外部ドメイン] タブを選択し、送信者の [スプーフィングが許可されていますか \>  \>  \>  \>  \> **?**   ] の値を確認します。

- PowerShell で次のコマンドを実行して、スプーフィングが許可されている送信者とスプーフィングを許可されていない送信者を表示します。

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- PowerShell で次のコマンドを実行して、すべてのスプーフィングされた送信者の一覧を CSV ファイルにエクスポートします。

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- セキュリティ & コンプライアンス センターで、脅威 **管理** ポリシーのフィッシング対策または ATP フィッシング対策に移動し、次のいずれかの手順 \>  \> を実行します。   

  - 一覧からポリシーを選択します。 表示されるフライアウトで、[Spoof] セクションの値を **確認** します。
  - [既定 **のポリシー] をクリックします**。 表示されるフライアウトで、[Spoof] セクションの値を **確認** します。

- Exchange Online PowerShell で、Office365 AntiPhish Default またはカスタム ポリシーの名前に置き換え、次のコマンドを実行して設定 \<Name\> を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>スプーフィングとフィッシングを管理するその他の方法

スプーフィングとフィッシング詐欺の防止に注意してください。 ドメインをスプーフィングしている送信者を確認し、組織に損害を与えないよう、関連する方法を次に示します。

- スプーフィング **メール レポートを確認します**。 このレポートは、多くの場合、スプーフィングされた送信者を表示および管理するために使用できます。 詳細については、「スプーフィング [検出レポート」を参照してください](view-email-security-reports.md#spoof-detections-report)。

- Sender Policy Framework (SPF) 構成を確認します。 SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。 Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。

- DomainKeys Identified Mail (DKIM) 構成を確認します。 SPF と DMARC に加えて DKIM を使用して、攻撃者がドメインから送信したようなメッセージを送信するのを防ぐ必要があります。 DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。 詳細については [、「DKIM を使用してカスタム](use-dkim-to-validate-outbound-email.md)ドメインから送信された送信電子メールを 365 Officeする」を参照してください。

- ドメイン ベースのメッセージ認証、レポート、および適合 (DMARC) 構成を確認します。 SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。 DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。 詳細については [、「DMARC を使用して Office 365](use-dmarc-to-validate-email.md)でメールを検証する」を参照してください。
