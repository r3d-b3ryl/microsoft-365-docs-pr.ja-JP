---
title: 'セキュリティ強化のために、Office 365 テナントを構成する '
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: このトピックでは、Microsoft 365 環境のセキュリティに影響を与えるテナント全体の設定の推奨構成について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6eff529a4ab2271df30579af227fe0c28691ae58
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286347"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>セキュリティ強化のために、Office 365 テナントを構成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

このトピックでは、Microsoft 365 環境のセキュリティに影響を与えるテナント全体の設定の推奨構成について説明します。 セキュリティニーズに必要なセキュリティは、多かれ少なかれ必要になる場合があります。 これらの推奨事項を開始点として使用します。

## <a name="check-office-365-secure-score"></a>365 Office スコアを確認する

Office 365 セキュア スコアは、通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てる。 まず、現在のスコアをメモします。 テナント全体の設定を調整すると、スコアが向上します。 目標は、最大スコアを達成するのではなく、ユーザーの生産性に悪影響を及ぼしない環境を保護する機会に注意を向けるという点です。 [「Microsoft セキュア スコア」を参照してください](../mtp/microsoft-secure-score.md)。

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターで脅威管理ポリシーを調整する

Microsoft 365 セキュリティ センターには、環境を保護する機能が含まれています。 また、監視とアクションの実行に使用できるレポートとダッシュボードも含まれています。 一部の領域には、既定のポリシー構成があります。 一部の領域には、既定のポリシーやルールが含まれます。 脅威管理の下にあるこれらのポリシーにアクセスして、より安全な環境に対する脅威管理設定を調整します。

****

|分野|既定のポリシーが含まれています|推奨事項|
|---|---|---|
|**フィッシング詐欺対策**|はい|カスタム ドメインがある場合は、CEO などの最も重要なユーザーの電子メール アカウントを保護し、ドメインを保護するために、既定のフィッシング対策ポリシーを構成します。 <p> [Office 365](set-up-anti-phishing-policies.md)でフィッシング対策ポリシーを確認し[、「EOP](configure-anti-phishing-policies-eop.md)でフィッシング対策ポリシーを構成する」または[「Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)でフィッシング対策ポリシーを構成する」を参照してください。|
|**マルウェア対策エンジン**|はい| 既定のポリシーを編集します。 <ul><li>一般的な添付ファイルの種類フィルター: オン</li></ul> <p> カスタム マルウェア フィルター ポリシーを作成し、組織内の指定したユーザー、グループ、またはドメインに適用することもできます。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[マルウェア対策保護](anti-malware-protection.md)</li><li>[マルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)</li></ul>|
|**Microsoft Defender for Office 365 の安全な添付ファイル**|いいえ|[安全な添付ファイル] のメイン ページで、[ **グローバル設定]** をクリックし、次の設定をオンにします。 <ul><li>**SharePoint、OneDrive、Microsoft Teams 用の Microsoft Defender for Office 365 を有効にする**</li></ul> <p> 次の設定を使用して安全な添付ファイル ポリシーを作成します。 <ul><li> **ブロック**: 不明 **なマルウェアの** 応答として [ブロック] を選択します。</li><li>**リダイレクトを** 有効にする : このボックスをオンにして、管理者アカウントや検疫アカウントなどのメール アドレスを入力します。</li><li>**添付ファイルのマルウェア スキャンがタイム アウトした場合、またはエラーが発生** した場合は、上記の選択を適用します。このチェック ボックスをオンにします。</li><li>**_適用:_***受信者のドメインがドメイン** \> を選択します。</li></ul> <p> 詳細: [SharePoint、OneDrive、Microsoft Teams](atp-for-spo-odb-and-teams.md) の安全な添付ファイルと安全な添付ファイル [ポリシーの設定](set-up-atp-safe-attachments-policies.md)|
|**Microsoft Defender for Office 365 の安全なリンク**|はい|[安全なリンク] のメイン ページで、[グローバル設定] **をクリックします**。 <ul><li>**安全なリンクを使用する: Office 365** アプリケーション: この設定がオンになっていることを確認します。</li><li>**ユーザーが [安全なリンク] をクリック** しても追跡しない : この設定をオフにすると、ユーザーのクリックを追跡できます。</li></ul> <p> 次の設定を使用して、安全なリンク ポリシーを作成します。 <ul><li>**Select the action for unknown potentially malicious URLs in messages**: Verify this setting is **On**.</li><li>**Microsoft Teams 内の不明な URL または悪意のある** 可能性のある URL に対するアクションを選択します。この設定がオンになっていないか確認 **します**。</li><li>**ファイルを指す疑わしいリンクや** リンクに対してリアルタイム URL スキャンを適用する: このボックスをオンにします。</li><li>**メッセージを配信する前に URL** のスキャンが完了するのを待ちます。このボックスをオンにします。</li><li>**組織内で送信された電子メール メッセージに安全なリンクを適用** する: このボックスをオンにします。</li><li>**ユーザーがクリックして元の URL にアクセスできない**: このボックスをオンにします。</li><li>**適用:****受信者のドメインがドメイン** \> を選択します。</li></ul> <p> 詳細: [安全なリンク ポリシーを設定します](set-up-atp-safe-links-policies.md)。|
|**スパム対策 (メール フィルター)**|はい| 注意する必要があります。 <ul><li>スパムが多すぎます - カスタム設定を選択し、既定のスパム フィルター ポリシーを編集します。</li><li>スプーフィング インテリジェンス - ドメインをスプーフィングしている送信者を確認します。 これらの送信者をブロックまたは許可します。</li></ul> <p> 詳細: [Microsoft 365 電子メールのスパム対策保護](anti-spam-protection.md)。|
|***電子メール認証***|はい|電子メール認証では、ドメイン ネーム システム (DNS) を使用して、電子メールの送信者に関する確認可能な情報を電子メール メッセージに追加します。 Microsoft 365 は既定のドメイン (onmicrosoft.com) の電子メール認証を設定しますが、Microsoft 365 管理者はカスタム ドメインに対して電子メール認証を使用できます。 次の 3 つの認証方法が使用されます。 <ul><li>Sender Policy Framework (または SPF)。</li><ul><li>セットアップについては [、「Microsoft 365 で SPF をセットアップしてスプーフィングを防止する」を参照してください](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</li></ul> <li>DomainKeys Identified Mail (DKIM)。</li><ul><li>[「DKIM を使用してカスタム ドメインから送信される送信電子メールを検証する」を参照してください](use-dkim-to-validate-outbound-email.md)。</li><li>DKIM を構成した後、セキュリティ センターで有効にしてください。</li></ul><li>ドメイン ベースのメッセージ認証、レポート、および適合性 (DMARC)。</li><ul><li>DMARC セットアップでは [、DMARC を使用して Microsoft 365 でメールを検証します](use-dmarc-to-validate-email.md)。</li></ul></ul>|
|

> [!NOTE]
> SPF、ハイブリッド展開、およびトラブルシューティングの非標準展開の場合: Microsoft [365 が Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)を使用してスプーフィングを防止する方法。

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>セキュリティ/コンプライアンス センターでダッシュボードとレポートを表示する

環境の正常性の詳細については、以下のレポートとダッシュボードを参照してください。 これらのレポートのデータは、組織が 365 サービスを使用するOfficeになります。 今のところ、監視およびアクションを実行できる機能について理解してください。 詳細については [、「Microsoft 365 セキュリティ/コンプライアンス センターのレポート」を参照してください](../../compliance/reports-in-security-and-compliance.md)。

****

|ダッシュボード|説明|
|---|---|
|[脅威管理ダッシュボード](security-dashboard.md)|セキュリティセンターの [脅威の管理] セクションで、このダッシュボードを使用して、既に処理されている脅威を確認し、ビジネスをセキュリティ保護するために既に実行されている脅威の調査と対応の機能をビジネスの意思決定者に報告するための便利なツールとして使用します。|
|[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)|これは、セキュリティ センター **の脅威管理** セクションにも含まれる。 テナントに対する攻撃を調査または経験している場合は、エクスプローラー (またはリアルタイムの検出) を使用して脅威を分析します。 エクスプローラー (およびリアルタイム検出レポート) には、時間のときにおける攻撃の量が表示され、脅威ファミリや攻撃者のインフラストラクチャなどによってこのデータを分析できます。 インシデント リストに不審なメールをマークできます。|
|レポート - ダッシュボード|セキュリティ センター **の [レポート** ] セクションで、SharePoint Online 組織と Exchange Online 組織の監査レポートを表示します。 また、[レポートの表示] ページから Azure Active Directory (Azure AD) ユーザー サインイン レポート、ユーザー アクティビティ レポート、Azure AD 監査ログに **アクセス** することもできます。|
|

![セキュリティ センター ダッシュボード](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>追加の Exchange Online テナント全体の設定を構成する

Exchange 管理センターのセキュリティと保護のコントロールの多くは、セキュリティ センターにも含まれています。 これらの構成は両方の場所で行う必要があります。 推奨される追加設定を次に示します。

****

|分野|既定のポリシーが含まれています|推奨事項|
|---|---|---|
|**メール フロー** (メール フロー ルール (トランスポート ルールとも呼ばれる)|いいえ|実行可能ファイルの種類をブロックしてランサムウェアから保護し、マクロを含むファイルの種類Officeルールを追加します。 詳細については、「メール フロー ルールを [使用して Exchange Online でメッセージの添付ファイルを検査する」を参照してください](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。 <p> 次の追加トピックを参照してください。 <ul><li>[ランサムウェアから保護する](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Microsoft 365 のマルウェアとランサムウェアからの保護](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Office 365 でランサムウェア攻撃から回復する](recover-from-ransomware.md)</li></ul> <p> 外部ドメインへの電子メールの自動転送を防止するメール フロー ルールを作成します。 詳細については、「セキュア スコア [によるクライアント外部転送ルールの軽減」を参照してください](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。 <p> 詳細: [Exchange Online のメール フロー ルール (トランスポート ルール)](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**モダン認証を有効にする**|いいえ|多要素認証 (MFA) を使用するには、最新の認証が必要です。 メールを含むクラウド リソースへのアクセスをセキュリティで保護するには、MFA をお勧めします。 <p> 次のトピックを参照してください。 <ul><li>[Exchange Online での最新認証の有効化または無効化](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online: テナントで最新の認証を有効にする](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> モダン認証は、2016 Office SharePoint Online、OneDrive for Business に対して既定で有効になっています。 <p> 詳細: [2016](../../enterprise/modern-auth-for-office-2013-and-2016.md)年 2 月のクライアント アプリOffice 2013および Office認証のしくみ|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>SharePoint 管理センターでテナント全体の共有ポリシーを構成する

ベースライン保護から始まる、より高いレベルの保護で SharePoint チーム サイトを構成するための Microsoft の推奨事項。 詳細については、SharePoint サイトとファイルをセキュリティ保護するための [ポリシーの推奨事項を参照してください](sharepoint-file-access-policies.md)。

ベースライン レベルで構成された SharePoint チーム サイトでは、匿名アクセス リンクを使用して外部ユーザーとファイルを共有できます。 この方法は、電子メールでファイルを送信する代わりに推奨されます。

ベースライン保護の目標をサポートするには、ここで推奨されるテナント全体の共有ポリシーを構成します。 個々のサイトの共有設定は、このテナント全体のポリシーよりも制限が厳しい場合がありますが、制限が厳しめになる可能性があります。

****

|分野|既定のポリシーが含まれています|推奨事項|
|---|---|---|
|**共有** (SharePoint Online と OneDrive for Business)|はい|外部共有は既定で有効になっています。 これらの設定をお勧めします。 <ul><li>認証された外部ユーザーへの共有と匿名アクセス リンクの使用を許可します (既定の設定)。</li><li>匿名アクセス リンクは、この日数で期限切れになります。 必要に応じて、30 日などの数値を入力します。</li><li>既定のリンクの種類 - [内部] (組織内のユーザーのみ) を選択します。 匿名リンクを使用して共有するユーザーは、共有メニューからこのオプションを選択する必要があります。</li></ul> <p> 詳細: [外部共有の概要](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

SharePoint 管理センターと OneDrive for Business 管理センターには、同じ設定が含まれます。 どちらの管理センターの設定も両方に適用されます。

## <a name="configure-settings-in-azure-active-directory"></a>Azure Active Directory で設定を構成する

より安全な環境のためにテナント全体のセットアップを完了するには、Azure Active Directory のこれら 2 つの領域にアクセスしてください。

### <a name="configure-named-locations-under-conditional-access"></a>名前付き場所を構成する (条件付きアクセスで)

セキュリティで保護されたネットワーク アクセスを持つオフィスが組織に含まれる場合は、信頼できる IP アドレス範囲を名前付き場所として Azure Active Directory に追加します。 この機能は、サインイン リスク イベントで報告された誤検知の数を減らすのに役立ちます。

参照: [Azure Active Directory の名前付き場所](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>モダン認証をサポートしないアプリをブロックする

多要素認証には、最新の認証をサポートするアプリが必要です。 条件付きアクセス ルールを使用して、モダン認証をサポートしていないアプリをブロックすることはできません。

セキュリティで保護された環境では、最新の認証をサポートしていないアプリの認証を無効にしてください。 これは、近日公開されるコントロールを使用して Azure Active Directory で行います。

その間に、SharePoint Online と OneDrive for Business でこれを実現するには、次のいずれかの方法を使用します。

- PowerShell の使用については、「 [モダン認証 (ADAL) を使用しないアプリをブロックする」を参照してください](https://docs.microsoft.com/mem/intune/protect/app-modern-authentication-block)。

- これは、SharePoint 管理センターの [デバイス アクセス] ページで構成します。 "最新の認証を使用しないアプリからのアクセスを制御する" [ブロック] を選択します。

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Cloud App Security または Office 365 Cloud App Security の使用を開始する

365 Cloud App Security Office使用して、リスクを評価し、疑わしいアクティビティについて警告し、自動的にアクションを実行します。 365 E5 Officeが必要です。

または、Microsoft Cloud App Security を使用して、アクセスが許可された後でも、より深い可視性を得たり、包括的な制御を行い、Office 365 を含むすべてのクラウド アプリケーションの保護を強化したりします。

このソリューションでは EMS E5 プランをお勧めしています。そのため、環境内の他の SaaS アプリケーションで使用できるよう、Cloud App Security から開始することをお勧めします。 既定のポリシーと設定から開始します。

詳しくは、以下の資料を参照してください。

- [Cloud App Security を展開する](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Microsoft Cloud App Security の詳細情報](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Cloud App Security とは](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security ダッシュボード](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>その他のリソース

次の記事とガイドでは、Microsoft 365 環境をセキュリティで保護するための追加の定例情報を提供します。

- [選挙運動、非営利](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) 団体、その他のアジャイル組織向け Microsoft セキュリティ ガイダンス (これらの推奨事項は、任意の環境、特にクラウド専用環境で使用できます)

- [ID とデバイスの推奨される](microsoft-365-policies-configurations.md) セキュリティ ポリシーと構成 (これらの推奨事項には、FS 環境のADが含まれます)
