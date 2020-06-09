---
title: スプーフィング インテリジェンスを設定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
description: 管理者は、特定のスプーフィングされた送信者を許可またはブロックする Exchange Online Protection (EOP) のスプーフィングインテリジェンスについて学ぶことができます。
ms.openlocfilehash: fe1e8f8a2e9f0cc792dc802ea5c7362af00687ae
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613242"
---
# <a name="configure-spoof-intelligence-in-eop"></a>EOP でスプーフィングインテリジェンスを構成する

Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange Online メールボックスを使用していない場合、受信電子メールメッセージは2018年10月の間に EOP によって自動的に保護されます。365 EOP は、組織のフィッシングに対する全体的な防衛の一環としてスプーフィングインテリジェンスを使用します。 詳細については、「 [EOP でのスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。

送信者が電子メールアドレスをスプーフすると、組織のドメインのいずれかのユーザー、または組織に電子メールを送信する外部ドメインのユーザーのように見えます。 スパムやフィッシング詐欺メールを送信するための送信者スプーフィングを行う攻撃者は、ブロックする必要があります。 しかし、正当な送信者がスプーフィングになっているシナリオもあります。 例:

- 内部ドメインのスプーフィングの正当なシナリオ:

  - サードパーティの送信者は、ドメインを使用して、会社の投票のために自分の従業員に一括メールを送信します。

  - 外部企業は、ユーザーの代わりに広告や製品の更新を生成して送信します。

  - アシスタントは、組織内の他のユーザーに対して定期的に電子メールを送信する必要があります。

  - 内部アプリケーションが電子メール通知を送信します。

- 外部ドメインをスプーフィングするための正当なシナリオ:

  - 送信者は、メーリングリスト (ディスカッションリストとも呼ばれます) 上にあり、メーリングリストは元の送信者からメーリングリストのすべての参加者に電子メールを中継します。

  - 外部企業は、別の会社に代わって電子メールを送信します (たとえば、自動化されたレポートや、サービスとしてのソフトウェア会社など)。

スプーフィングインテリジェンス、特に既定の (および唯一の) スプーフィングインテリジェンスポリシーにより、正当な送信者が送信したスプーフィングされた電子メールが EOP スパムフィルターや外部の電子メールシステムでキャッチされないようにしながら、スパムまたはフィッシング攻撃からユーザーを保護することができます。

セキュリティ & コンプライアンスセンター、または PowerShell (exchange online のメールボックスを使用する Microsoft 365 組織の場合は exchange online PowerShell、exchange online メールボックスを使用していない組織の場合は、スタンドアロン EOP PowerShell) で、スプーフィングインテリジェンスを管理できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。 **フィッシング対策**ページに直接移動するには、を使用 <https://protection.office.com/antiphishing> します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 スプーフィングインテリジェンスポリシーを変更したり、スプーフィングインテリジェンスを有効または無効にしたりするには、**組織の管理**役割グループまたは**セキュリティ管理者**役割グループのメンバーである必要があります。 スプーフィングインテリジェンスポリシーへの読み取り専用アクセスでは、**セキュリティリーダー**役割グループのメンバーである必要があります。 セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。

- スプーフィングインテリジェンスに推奨される設定については、「 [EOP default フィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)」を参照してください。

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>セキュリティ & コンプライアンスセンターを使用してスプーフィングされた送信者を管理する

> [!NOTE]
> Microsoft 365 Enterprise E5 サブスクリプションを使用している場合、または Office 365 Advanced Threat Protection (Office 365 ATP) アドオンを個別に購入した場合は、[スプーフィングインテリジェンスの洞察](walkthrough-spoof-intelligence-insight.md)を通じてドメインをスプーフィングしている送信者を管理することもできます。

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. [**スパム対策設定**] ページで、[ ![ 展開] アイコンをクリックして [ ](../../media/scc-expand-icon.png) **スプーフィングインテリジェンスポリシー**] を展開します。

   ![スプーフィングインテリジェンスポリシーを選択する](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. 次のいずれかの選択を行います。

   - **新しい送信者を確認する**
   - **レビュー済みの送信者を表示する**

4. 表示される [ユーザー] ポップアップの**スプーフィングを許可するかどう**かを決定するには、次のタブのいずれかを選択します。

   - **ドメイン**: 送信者が内部ドメイン内のユーザーを偽装します。
   - **外部ドメイン**: 送信者は外部ドメインのユーザーを偽装します。

5. [ ![ ](../../media/scc-expand-icon.png) **スプーフィングが許可さ**れていますか?] 列の [展開] アイコンをクリックします。 スプーフィングされた送信者を許可する場合は [**はい]** を選択し、メッセージをスプーフィングとしてマークする場合は [**いいえ**] を選択します。 このアクションは、既定のフィッシング対策ポリシーまたはカスタムの ATP のフィッシング対策ポリシーによって制御されます (既定値は **[迷惑メールフォルダーにメッセージを移動**します)]。 詳細については、「[フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。

   ![スプーフィングされた送信者のポップアップと、送信者がスプーフィングを許可するかどうかを示すスクリーンショット](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   表示される列と値については、次の一覧で説明します。

   - **偽装ユーザー**: スプーフィングされているユーザーアカウント。 これは、 `5322.From` 電子メールクライアントに表示される差出人アドレス (アドレスとも呼ばれます) のメッセージ送信者です。 このアドレスの有効性は、SPF によってチェックされません。

     - [**自分のドメイン**] タブの値に1つの電子メールアドレスが含まれている場合、または送信元の電子メールサーバーが複数のユーザーアカウントを偽装している場合は、複数のユーザーアカウントが含ま**れています。**

     - [**外部ドメイン**] タブの値には、完全な電子メールアドレスではなく、偽装されたユーザーのドメインが含まれています。

   - [**インフラストラクチャの送信**]: 送信元の電子メールサーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) にあるドメイン、またはソースに PTR レコードがない場合は ip アドレス。

     メッセージソースとメッセージ送信者の詳細については、「[電子メールメッセージの標準の概要](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)」を参照してください。

   - **メッセージ数**: 過去30日間に、指定したスプーフィングされた送信者または送信者を含む組織への送信インフラストラクチャからのメッセージの数。

   - **ユーザーの苦情**: 過去30日間にこの送信者に対してユーザーが提出した苦情。 通常、苦情は Microsoft への迷惑メール送信の形式です。

   - **認証結果**: 次のいずれかの値です。

      - **成功**: 送信者が送信者の電子メール認証チェック (SPF または dkim) を通過しました。
      - **失敗**しました。送信者は EOP の認証チェックに失敗しました。
      - **Unknown**: これらのチェックの結果は不明です。

   - **Decision set by**: 送信インフラストラクチャがユーザーのスプーフィングを許可されているかどうかを示します。

       - **スプーフィングインテリジェンスポリシー** (自動)
       - **管理者**(手動)

   - **最終表示**日: 偽装されたユーザーを含む送信元インフラストラクチャからメッセージが受信された最後の日付。

   - **スプーフィングが許可されますか?**: ここに表示される値は次のとおりです。

     - **Yes**: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージが許可され、スプーフィングされた電子メールとして扱われることはありません。

     - **いいえ**: スプーフィングされたユーザーと送信元インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。 このアクションは、既定のフィッシング対策ポリシーまたはカスタムの ATP のフィッシング対策ポリシーによって制御されます (既定値は **[迷惑メールフォルダーにメッセージを移動**します)]。 詳細については、次のセクションを参照してください。

     - **一部のユーザー** ([**自分のドメイン**] タブのみ): 送信元のインフラストラクチャは複数のユーザーをスプーフィングしています。これには、一部のスプーフィングされたユーザーが許可されています。 特定のアドレスを表示するには、[**詳細**] タブを使用します。

6. ページの下部にある [**保存**] をクリックします。

## <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell を使用してスプーフィングされた送信者を管理する

スプーフィングインテリジェンスで許可された送信者と受信拒否送信者を表示するには、次の構文を使用します。

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

この例では、ドメイン内のユーザーのスプーフィングを許可されているすべての送信者に関する詳細情報を返します。

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

構文およびパラメーターの詳細については、「 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)」を参照してください。

許可およびブロックされる送信者をスプーフィングインテリジェンスで構成するには、次の手順を実行します。

1. 検出されたスプーフィングされた送信者の現在のリストを取得するには、 **get-phishfilterpolicy**コマンドレットの出力を CSV ファイルに書き込みます。

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. CSV ファイルを編集して、 **SpoofedUser** (メールアドレス) および**allowedtospoof** (Yes または No) の値を追加または変更します。 ファイルを保存し、ファイルを読み取って、コンテンツをという名前の変数として保存し `$UpdateSpoofedSenders` ます。

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 変数を使用し `$UpdateSpoofedSenders` て、スプーフィングインテリジェンスポリシーを構成します。

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

構文およびパラメーターの詳細については、「 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)」を参照してください。

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>セキュリティ & コンプライアンスセンターを使用してスプーフィングインテリジェンスを構成する

スプーフィングインテリジェンスの構成オプションの詳細については、「[フィッシング対策ポリシー」の「スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。

スプーフィングインテリジェンスの設定は、既定のフィッシング対策ポリシーとカスタムポリシーで構成できます。 サブスクリプションに基づく手順については、以下のいずれかのトピックを参照してください。

- [EOP でフィッシング対策ポリシーを構成](configure-anti-phishing-policies-eop.md)します。

- [Microsoft 365 で ATP のフィッシング対策ポリシーを構成](configure-atp-anti-phishing-policies.md)します。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

許可されている送信者とスプーフィングが許可されていない送信者、およびスプーフィングインテリジェンスの設定が構成済みであるというスプーフィングインテリジェンスが構成されていることを確認するには、次のいずれかの手順を使用します。

- [セキュリティ & コンプライアンスセンター] で、[**脅威の管理**ポリシーのスパム対策]、 \> **Policy** \> **Anti-spam** \> [**スプーフィングインテリジェンスポリシー**の選択] の \> 順**に**選択します \> 。 [**ドメイン**または**外部ドメイン**] タブを選択し、[**スプーフィングを許可する**] の値を確認します。

- PowerShell で、次のコマンドを実行して、許可されている、またはスプーフィングが許可されていない送信者を表示します。

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

- セキュリティ & コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \> の**フィッシング対策**] または [ **ATP のフィッシング対策**] に移動して、次のいずれかの手順を実行します。  

  - リストからポリシーを選択します。 表示されたポップアップで、[**スプーフ**] セクションの値を確認します。
  - [**既定のポリシー**] をクリックします。 表示されたポップアップで、[**スプーフ**] セクションの値を確認します。

- Exchange Online PowerShell で、 \<Name\> Office365 フィッシング対策 Default またはカスタムポリシーの名前に置き換え、次のコマンドを実行して設定を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>スプーフィングとフィッシングを管理するその他の方法

スプーフィングとフィッシングの保護については、入念に行ってください。 ここでは、ドメインをスプーフィングしている送信者をチェックして、組織の損害を防ぐ方法について説明します。

- **スプーフィングメールレポート**を確認します。 このレポートは多くの場合、スプーフィングされた送信者を表示して管理するために使用できます。 詳細については、「[スプーフィング検出レポート](view-email-security-reports.md#spoof-detections-report)」を参照してください。

- Sender Policy Framework (SPF) 構成を確認します。 SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。 Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。

- DomainKeys が識別されたメール (DKIM) 構成を確認します。 SPF および DMARC に加えて DKIM を使用して、攻撃者がドメインから受信したように見えるメッセージを送信できないようにする必要があります。 DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。 詳細については、「 [DKIM を使用して、Office 365 でカスタムドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)」を参照してください。

- ドメインベースのメッセージ認証、レポート、および準拠 (DMARC) 構成を確認します。 SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。 DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。 詳細については、「 [USE DMARC to validate email In Office 365](use-dmarc-to-validate-email.md)」を参照してください。
