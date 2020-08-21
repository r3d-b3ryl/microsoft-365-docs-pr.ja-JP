---
title: スプーフィング インテリジェンスを設定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、特定のスプーフィングされた送信者を許可またはブロックできる、Exchange Online Protection (EOP) のスプーフィング インテリジェンスについて学習することができます。
ms.openlocfilehash: 66cfc419c3e2f3a5dd8ad45cdb9fe651b613679b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826579"
---
# <a name="configure-spoof-intelligence-in-eop"></a>EOP でスプーフィング インテリジェンスを構成する

Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online のメールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、受信電子メール メッセージは、2018 年 10 月の EOP によりスプーフィングから自動的に保護されます。 EOP は、フィッシングに対する組織の全体的な防が層となって、スプーフィング インテリジェンスを使用します。 詳細については [、EOP のスプーフィング対策保護を参照してください](anti-spoofing-protection.md)。

送信者がメール アドレスを偽フィングする際、組織のドメインの 1 つに含むユーザー、または組織に電子メールを送信する外部ドメインのユーザーのように見えるように見える。 スパムまたはフィッシング メールを送信するために偽の送信者を偽プする攻撃者はブロックする必要があります。 ただし、正当な送信者がスプーフィングしている場合があります。 たとえば、次のようにします。

- 内部ドメインのスプーフィングに対する正当なシナリオ:

  - サード パーティの送信者は、ドメインを使って、会社のポーリングに対して自分の従業員にバルク メールを送信します。
  - 外部の会社が、ユーザーに代わって広告プログラムや製品更新プログラムを生成し、送信します。
  - 組織内の別のユーザーに対してアシスタントがメールを送信する必要がある場合。
  - 内部アプリケーションが、電子メール通知を送信します。

- 外部ドメインのスプーフィングに対する正当なシナリオ:

  - 送信者が、メール リスト (ディスカッション リストとも呼ばれる) に登録され、その人は、元の送信者からの電子メールを、メール リストに登録されたすべての参加者に中継します。
  - 外部の会社が、他の会社 (自動化レポートやサービスとしてのソフトウェア会社など) の代わりに電子メールを送信する。

スプーフィング インテリジェンス(特にデフォルトのスプーフィング インテリジェンス ポリシー) は、正当な送信者によって送信されたなりすましメールが EOP スパム フィルターや外部電子メール システムで検出されないようにしながら、スパムやフィッシング攻撃からユーザーを保護できます。

スプーフィング インテリジェンスは、セキュリティ & コンプライアンス センター、または PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織用の Exchange Online PowerShell、Exchange Online メールボックスを持たない組織の場合はスタンドアロン EOP PowerShell) で管理できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。 フィッシング **対策ページに直接移動するには** 、次の手順を使用します <https://protection.office.com/antiphishing> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - スプーフィング インテリジェンス ポリシーを変更したり、スプーフィング インテリジェンスを有効または無効にしたりするには、次のいずれかの役割グループのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - スプーフィング インテリジェンス ポリシーに読み取り専用アクセスするには、次の役割グループのいずれかのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

- スプーフィング インテリジェンスについて推奨される設定については [、EOP の既定のフィッシング対策ポリシー設定を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>セキュリティ コンプライアンス センターを&、スプーフィングされた送信者を管理する

> [!NOTE]
> Microsoft 365 Enterprise E5 サブスクリプションをお持つの場合、または Office 365 Advanced Threat Protection (Office 365 ATP) アドオンを別々に購入している場合は、なりすましインテリジェンス分析情報を使用してドメイン [偽の送信者を管理することもできます](walkthrough-spoof-intelligence-insight.md)。

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [スパム対策 **の設定] ページで、[展開** ] アイコン ![ を ](../../media/scc-expand-icon.png) クリックして、ス **プーフィング インテリジェンス ポリシーを拡張します**。

   ![スプーフィング インテリジェンス ポリシーを選択する](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. 次のいずれかの選択を行います。

   - **新しい送信者の確認**
   - **既に確認済みの送信者を表示する**

4. 表示される **ユーザーのポップアップを、これらの送信者** に対してスプーフィングが許可されているかどうかを決定するには、[次のいずれかのタブ] を選択します。

   - **Your Domains**: Senders spoofing users in your internal domains.
   - **外部ドメイン**: 外部ドメインのユーザースプーフィング ユーザー。

5. [ ![ スプー ](../../media/scc-expand-icon.png) フィングの **許可] 列の [展開] アイコンをクリック** します。 スプ **ー** フィングされた送信者を許可する場合は [はい] を、 **メッセージをスプー** フィングに指定するには [いいえ] を選んでください。 アクションは、既定のフィッシング対策ポリシー、またはカスタム ATP フィッシング対策ポリシーによって制御されます (既定値は **、[メッセージを迷惑メール フォルダーに移動] です**)。 詳細については、フィッ [シング対策ポリシーでのスプーフィング設定に関するトピックを参照してください](set-up-anti-phishing-policies.md#spoof-settings)。

   ![なりすましたされた送信者のポップアップ、および送信者がスプーフィングを許可されているかどうかを示すスクリーンショット](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   表示される列と値の一覧を次に示します。

   - **スプーフィング**されたユーザー: スプーフィングされているユーザー アカウント。 これは、電子メール クライアントに表示される差出人アドレス ( `5322.From` アドレスとも呼ばれる) のメッセージ送信者です。 このアドレスの有効性は SPF によってチェックされません。

     - [Your **Domains] タブでは** 、値に単一のメール アドレスが含まれます。または、ソース メール サーバーが複数のユーザー アカウントをスプーフィングしている場合は、複数 **の電子メール アドレスが含まれます**。

     - この値 **には、外部ドメイン** の完全な電子メール アドレスは含まれるのでない、スプーフィングされたユーザーのドメインが含まれます。

   - **Sending Infrastructure**(送信元インフラストラクチャ): 送信元の電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) にあるドメイン、またはソースに PTR レコードがない場合は IP アドレス。

     メッセージの送信元とメッセージ送信者の詳細については、「電子メール [メッセージの基準の概要」を参照してください](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

   - **メッセージ数**: 過去 30 日間の指定されたなりすき送信者または送信者が含まれる、送信インフラストラクチャから組織内へのメッセージの数。

   - **ユーザーの補足の数**: 過去 30 日以内にユーザーによって行われた相割合 通常、補足は Microsoft への迷惑メールの提出の形式です。

   - **認証の結果**: 次のいずれかの値です。

      - **Passed:** 送信者が送信者のメール認証チェック (SPF または DKIM) をパスしました。
      - **失敗**: 送信者が EOP の送信者認証チェックに失敗しました。
      - **Unknown:** これらのチェックの結果が不明です。

   - **Decision set by:** 送信元インフラストラクチャがユーザーのスプーフィングを許可されているかどうかを決定したユーザーを示します。

       - **スプーフィング インテリジェンス ポリシー** (自動)
       - **管理者** (手動)

   - **最後の確認日時**: スプーフィングされたユーザーを含む送信インフラストラクチャからメッセージを受信した日付です。

   - **スプーフィングは許可されていますか?**:次のような値があります。

     - **はい**: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは許可され、スプーフィングされたメールとしては処理されません。

     - **い**いえ: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィング済みとしてマークされます。 アクションは、既定のフィッシング対策ポリシー、またはカスタム ATP フィッシング対策ポリシーによって制御されます (既定値は **、[メッセージを迷惑メール フォルダーに移動] です**)。 詳細については、次のセクションを参照してください。

     - **一部の** ユーザー **([ドメイン]** タブのみ): 送信インフラストラクチャは複数のユーザーにスプーフィングを行う状態になり、スプーフィングされたユーザーの一部は許可され、他のユーザーは許可されません。 特定のアドレス **を確認するには** 、[詳細] タブを使用します。

6. ページの下部にある [**保存**] をクリックします。

## <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell を使用して、スプーフィングされた送信者を管理する

スプーフィング インテリジェンスで許可またはブロックする差出人を表示するには、次の構文を使用します。

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

この例では、ドメイン内のユーザーへのスプーフィングが許可されているすべての送信者に関する詳細情報を返します。

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

構文およびパラメーターの詳細については [、「Get-PhishFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)。

スプーフィング インテリジェンスで許可およびブロックする差出人を構成するには、次の手順を実行します。

1. **Get-PhishFilterPolicy**コマンドレットの出力を CSV ファイルに書き込み、検出されたスプーフィングされた送信者の現在のリストをキャプチャします。

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. CSV ファイルを編集して **、SpoofedUser** (メール アドレス) と **AllowedToSpoof** (Yes または No) の値を追加または変更します。 ファイルを保存してファイルを読み取り、その内容を次の名前の変数として保存します `$UpdateSpoofedSenders` 。

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. この変数を `$UpdateSpoofedSenders` 使用して、スプーフィング インテリジェンス ポリシーを構成します。

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

構文およびパラメーターの詳細については [、「Set-PhishFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)。

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>セキュリティ センター コンプライアンス センター&、スプーフィング インテリジェンスを構成する

スプーフィング インテリジェンスの構成オプションは、フィッシ [ング対策ポリシーのスプーフィング対策設定で説明されています](set-up-anti-phishing-policies.md#spoof-settings)。

スプーフィング インテリジェンス設定は、既定のフィッシング対策ポリシーで、さらにカスタム ポリシーで構成することもできます。 サブスクリプションに基づく手順については、次のいずれかのトピックを参照してください。

- [EOP でフィッシング対策ポリシーを構成する](configure-anti-phishing-policies-eop.md)。

- [Microsoft 365 で ATP フィッシング対策ポリシーを構成します](configure-atp-anti-phishing-policies.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

スプーフィングが許可されている送信者およびスプーフィングが許可されていない送信者に対して、スプーフィング インテリジェンスを構成したことを確認するには、次のいずれかの手順を使用します。

- セキュリティ & コンプライアンス センターで、脅威管理ポリシーのスパム対策ポリシーに移動**し、[** なりすでに確認した送信者に通知する] を選択し、[既に \> **Policy** \> **Anti-spam** \> **Spoof intelligence policy** \> **Show me senders I already reviewed** \> **[ドメインまたは外部ドメイン]****External Domains****Allowed to spoof?** タブを選択した場合は、[スプーフィングの許可] を確認します。

- PowerShell で次のコマンドを実行して、許可される送信者とスプーフィングが許可されない送信者を表示します。

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- PowerShell で次のコマンドを実行して、スプーフィングされたすべての送信者の一覧を CSV ファイルにエクスポートします。

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- Security & コンプライアンス センターで、**脅威管理**ポリシーのフィッシング対策または ATP フィッシング対策に \> **Policy** \> **Anti-phishing****移動**し、次のいずれかの手順を実行します。  

  - 一覧からポリシーを選択します。 表示されるポップアップで、Spoof セクションの値 **を確認** します。
  - [既定 **のポリシー] をクリックします**。 表示されるポップアップで、Spoof セクションの値 **を確認** します。

- Exchange Online PowerShell で \<Name\> 、Office365 AntiPhish Default またはカスタム ポリシーの名前に置き換え、次のコマンドを実行して設定を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>スプーフィングとフィッシングを管理するその他の方法

スプーフィングとフィッシング対策について詳しい説明を提供する。 ここでは、ドメインをなりすますようになり、組織を損な化しないようにする次のような関連する方法があります。

- なりすみ **メッセージのレポートを確認します**。 このレポートは、多くの場合、スプーフィングされた送信者を表示して管理できます。 詳細については、「なり [すみ」レポートを参照してください](view-email-security-reports.md#spoof-detections-report)。

- Sender Policy Framework (SPF) の構成を確認します。 SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。 Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。

- DomainKeys Identified Mail (DKIM) の構成を確認します。 ドメインから送信されたように見えるメッセージを攻撃者が送信するのを防ぐには、SPF と DMARC に加え、DKIM を使用する必要があります。 DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。 詳細については [、「DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する」を参照してください](use-dkim-to-validate-outbound-email.md)。

- ドメイン ベースのメッセージ認証、レポート、および Conformance (DMARC) の構成を確認します。 SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。 DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。 詳細については [、「DMARC を使用して、Office 365 で電子メールを検証する」を参照してください](use-dmarc-to-validate-email.md)。
