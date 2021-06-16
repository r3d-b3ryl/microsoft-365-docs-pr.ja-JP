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
description: このトピックでは、テナント環境のセキュリティに影響を与えるテナント全体の設定に対する推奨構成Microsoft 365説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 623ea316d1ad92790b8818504970a1d35401f617
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929577"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>セキュリティ強化のために、Office 365 テナントを構成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

このトピックでは、テナント環境のセキュリティに影響を与えるテナント全体の設定に対する推奨構成Microsoft 365説明します。 セキュリティニーズには、多かれ少なかれセキュリティが必要になる場合があります。 これらの推奨事項を開始点として使用します。

## <a name="check-office-365-secure-score"></a>セキュリティOffice 365スコアを確認する

Office 365Secure Score は、通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てる。 まず、現在のスコアをメモします。 テナント全体の設定を調整すると、スコアが向上します。 目標は、最大スコアを達成するのではなく、ユーザーの生産性に悪影響を及ぼしない環境を保護する機会を認識する方法です。 「Microsoft [Secure Score」を参照してください](../defender/microsoft-secure-score.md)。

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>Defender ポータルで脅威管理ポリシー Microsoft 365調整する

Defender Microsoft 365には、環境を保護する機能が含まれています。 また、監視とアクションの実行に使用できるレポートとダッシュボードも含まれています。 一部の領域では、既定のポリシー構成が使用されます。 一部の領域には、既定のポリシーやルールが含まれます。 脅威管理の下にあるこれらのポリシーにアクセスして、より安全な環境の脅威管理設定を調整します。

<br>

****

|分野|既定のポリシーを含む|推奨事項|
|---|---|---|
|**フィッシング対策**|はい|<ul><li>偽装保護 - Defender for Office 365 とカスタム ドメインがある場合は、既定のフィッシング対策ポリシーで偽装保護設定を構成して、CEO などの最も価値のあるユーザーの電子メール アカウントを保護し、ドメインを保護します。 詳細: [フィッシング対策ポリシーの](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 偽装設定と [偽装の分析情報](impersonation-insight.md)</li><li>スプーフィング インテリジェンス : ドメインをスプーフィングしている送信者を確認します。 これらの送信者をブロックまたは許可します。 詳細: [EOP のスプーフィン](learn-about-spoof-intelligence.md) グ インテリジェンスインサイトと [テナント許可/ブロック一覧の管理](tenant-allow-block-list.md)。</li></ul>|
|**マルウェア対策エンジン**|はい|既定のポリシーを編集します。 <ul><li>[共通 **の添付ファイルフィルターを有効にする] を選択します。**</li></ul> <p> カスタム マルウェア フィルター ポリシーを作成し、組織内の指定したユーザー、グループ、またはドメインに適用することもできます。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[マルウェア対策保護](anti-malware-protection.md)</li><li>[マルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)</li></ul>|
|**セーフMicrosoft Defender の添付ファイル (Office 365**|いいえ|[添付ファイル] のメイン ページセーフ[グローバル設定]**をクリックし**、次の設定をオンにします。 <ul><li>**SharePoint、OneDrive、Microsoft Teams 用の Microsoft Defender for Office 365 を有効にする**</li></ul> <p> 次の設定セーフ添付ファイル ポリシーを作成します。 <ul><li> **[ブロック**]: 不明 **なマルウェア応答** として [ブロック] を選択します。</li><li>**リダイレクトを有効** にする: このボックスをオンにして、管理者アカウントや検疫アカウントなどの電子メール アドレスを入力します。</li><li>**添付ファイルのマルウェア スキャンがタイム アウト** またはエラーが発生した場合は、上記の選択を適用します。このボックスをオンにします。</li><li>**_適用:_***受信者ドメインがドメイン** \> を選択します。</li></ul> <p> 詳細:[セーフ、SharePoint、OneDrive、Microsoft Teams](mdo-for-spo-odb-and-teams.md)の添付ファイルポリシーセーフ[設定](set-up-safe-attachments-policies.md)|
|**セーフMicrosoft Defender for Office 365**|はい|[リンク] のメイン ページセーフ[グローバル設定]**をクリックします**。 <ul><li>**[セーフを使用する: Office 365**: この設定がオンになっていることを確認します。</li><li>**ユーザーが [リンク] をクリックセーフ追跡** しない: ユーザーのクリックを追跡するには、この設定をオフにします。</li></ul> <p> 次の設定セーフリンク ポリシーを作成します。 <ul><li>**メッセージ内の不明な潜在的に悪意** のある URL のアクションを選択します。この設定が [オン] である必要 **があります**。</li><li>**[この設定が [オン**] に設定されている場合は、Microsoft Teamsまたは悪意のある可能性のある URL のアクションを選択 **します**。</li><li>**ファイルを指す疑わしいリンク** やリンクに対してリアルタイムの URL スキャンを適用する: このボックスをオンにします。</li><li>**メッセージを配信する前に URL** のスキャンが完了するのを待ちます。このボックスをオンにします。</li><li>**[セーフ組織内で送信された電子メール メッセージ** へのリンクを適用する: このボックスをオンにします。</li><li>**ユーザーに元の URL へのクリックを** 許可しない: このボックスをオンにします。</li><li>**適用先**: **受信者ドメインがドメイン** \> を選択します。</li></ul> <p> 詳細:[リンク ポリシーセーフ設定します](set-up-safe-links-policies.md)。|
|**スパム対策 (メール フィルター)**|はい| 監視する内容: スパムが多すぎます - カスタム設定を選択し、既定のスパム フィルター ポリシーを編集します。 詳細: Microsoft 365[スパム対策の保護](anti-spam-protection.md)。|
|***電子メール認証***|はい|電子メール認証では、ドメイン ネーム システム (DNS) を使用して、電子メールの送信者に関する電子メール メッセージに検証可能な情報を追加します。 Microsoft 365 (onmicrosoft.com) の電子メール認証を設定しますが、Microsoft 365管理者はカスタム ドメインに電子メール認証を使用できます。 3 つの認証方法が使用されます。 <ul><li>送信者ポリシー フレームワーク (または SPF)。</li><ul><li>セットアップについては、「スプーフィング[を防止するために、Microsoft 365 SPF をセットアップする」を参照してください](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</li></ul> <li>DomainKeys Identified Mail (DKIM)。</li><ul><li>[「DKIM を使用してカスタム ドメインから送信される送信メールを検証する」を参照してください](use-dkim-to-validate-outbound-email.md)。</li><li>DKIM を構成した後、Defender ポータルの Microsoft 365有効にしてください。</li></ul><li>ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC)</li><ul><li>DMARC セットアップでは[、DMARC を使用してメールを検証](use-dmarc-to-validate-email.md)Microsoft 365。</li></ul></ul>|
|

> [!NOTE]
> SPF、ハイブリッド展開、およびトラブルシューティングの非標準展開の場合: Microsoft 365 がスプーフィングを防止するために Sender [Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)を使用する方法。

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>Defender ポータルでダッシュボードとレポートMicrosoft 365表示する

環境の正常性の詳細については、これらのレポートとダッシュボードをご覧ください。 これらのレポートのデータは、組織がサービスを使用するOffice 365されます。 今のところ、監視およびアクションを実行できる機能について理解してください。 詳細については、「Defender ポータルの[レポート」をMicrosoft 365してください](../../compliance/reports-in-security-and-compliance.md)。

<br>

****

|ダッシュボード|説明|
|---|---|
|[脅威管理ダッシュボード](security-dashboard.md)|Microsoft 365  Defender ポータルの [脅威管理] セクションで、このダッシュボードを使用して、既に処理されている脅威を確認し、ビジネスをセキュリティで保護するために既に行っている脅威調査と対応機能についてビジネス意思決定者に報告するための便利なツールとして使用します。|
|[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)|これは、Defender ポータルの **[** 脅威の管理] Microsoft 365にも含まれる。 テナントに対する攻撃を調査または発生している場合は、エクスプローラー (またはリアルタイムの検出) を使用して脅威を分析します。 エクスプローラー (およびリアルタイム検出レポート) には、時間の過ぎた攻撃の量が表示され、脅威ファミリ、攻撃者インフラストラクチャなどによってこのデータを分析できます。 [インシデント] リストに不審なメールをマークできます。|
|レポート - ダッシュボード|Defender ポータル **の [** レポート] セクションMicrosoft 365、オンライン組織および組織の監査SharePoint表示Exchange Onlineします。 [レポートの表示] Azure Active Directory (Azure AD) ユーザー サインイン レポート、ユーザー アクティビティ レポート、Azure AD 監査ログに **アクセス** することもできます。|
|

![Microsoft 365Defender ポータル ダッシュボード](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>テナント全体のExchange Onlineを構成する

推奨される追加の設定を次に示します。

<br>

****

|分野|既定のポリシーを含む|推奨事項|
|---|---|---|
|**メール Flow** (メール フロー ルール (トランスポート ルールとも呼ばれる)|いいえ|実行可能ファイルの種類をブロックし、マクロを含むOfficeファイルの種類をブロックすることで、ランサムウェアから保護するためのメール フロー ルールを追加します。 詳細については、「メール フロー ルール[を使用してメッセージの添付ファイル](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)を調Exchange Online。 <p> 以下の追加トピックを参照してください。 <ul><li>[ランサムウェアから保護する](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[マルウェアとランサムウェアの保護 (Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[ユーザーのランサムウェア攻撃から回復Office 365](recover-from-ransomware.md)</li></ul> <p> メール フロー ルールを作成して、外部ドメインへのメールの自動転送を防止します。 詳細については、「Secure [Score を使用したクライアント外部転送ルールの緩和」を参照してください](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。 <p> 詳細: メール[フロー ルール (トランスポート](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)ルール) Exchange Online|
|**モダン認証を有効にする**|いいえ|モダン認証は、多要素認証 (MFA) を使用する前提条件です。 メールを含むクラウド リソースへのアクセスをセキュリティで保護するには、MFA をお勧めします。 <p> 以下のトピックを参照してください。 <ul><li>[Exchange Online での最新認証の有効化または無効化](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Businessオンライン: テナントで最新の認証を有効にする](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> 最新の認証は、2016 年のクライアント、Officeオンライン、および SharePointに対して既定でOneDrive for Business。 <p> 詳細: [2013 年および 2016 年Office 2016](../../enterprise/modern-auth-for-office-2013-and-2016.md)年のOffice認証のしくみ|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>管理センターでテナント全体の共有ポリシー SharePoint構成する

ベースライン保護から始まる、SharePointレベルの保護でチーム サイトを構成するための Microsoft の推奨事項。 詳細については、「サイトとファイル[のセキュリティ保護に関するSharePoint推奨事項」を参照してください](sharepoint-file-access-policies.md)。

SharePointレベルで構成されたチーム サイトでは、匿名アクセス リンクを使用して外部ユーザーとファイルを共有できます。 この方法は、電子メールでファイルを送信する代わりにお勧めします。

ベースライン保護の目標をサポートするには、ここで推奨されるテナント全体の共有ポリシーを構成します。 個々のサイトの共有設定は、このテナント全体のポリシーよりも制限が厳しい場合がありますが、より制限的ではありません。

<br>

****

|分野|既定のポリシーを含む|推奨事項|
|---|---|---|
|**共有**(SharePointオンラインとOneDrive for Business)|はい|外部共有は既定で有効になっています。 これらの設定をお勧めします。 <ul><li>認証された外部ユーザーへの共有と匿名アクセス リンクの使用を許可する (既定の設定)。</li><li>匿名アクセス リンクは、この数日間で期限切れになります。 必要に応じて、30 日などの数値を入力します。</li><li>既定のリンクの種類 - [内部] (組織内のユーザーのみ) を選択します。 匿名リンクを使用して共有するユーザーは、共有メニューからこのオプションを選択する必要があります。</li></ul> <p> 詳細: [外部共有の概要](/sharepoint/external-sharing-overview)|
|

SharePoint管理センターと管理センター OneDrive for Business同じ設定が含まれます。 どちらの管理センターの設定も両方に適用されます。

## <a name="configure-settings-in-azure-active-directory"></a>サーバーで設定を構成Azure Active Directory

テナント全体のセットアップを完了し、より安全な環境を実現Azure Active Directory、この 2 つの領域にアクセスしてください。

### <a name="configure-named-locations-under-conditional-access"></a>名前付き場所を構成する (条件付きアクセスの下で)

組織にセキュリティで保護されたネットワーク アクセスを持つオフィスが含まれる場合は、信頼できる IP アドレスの範囲を名前付Azure Active Directoryとして追加します。 この機能は、サインイン リスク イベントで報告された誤検知の数を減らすのに役立ちます。

参照:[名前の付いた場所 (Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>モダン認証をサポートしないアプリをブロックする

多要素認証には、最新の認証をサポートするアプリが必要です。 最新の認証をサポートしていないアプリは、条件付きアクセス ルールを使用してブロックできません。

セキュリティで保護された環境では、最新の認証をサポートしていないアプリの認証を無効にしてください。 この操作は、Azure Active Directory近日行うコントロールを使用して実行できます。

その間に、次のいずれかの方法を使用して、オンラインとオンラインのSharePoint実行OneDrive for Business。

- PowerShell を使用して、 [モダン認証 (ADAL) を使用しないアプリをブロックするを参照してください](/mem/intune/protect/app-modern-authentication-block)。

- これを構成するには、SharePoint管理センターの [デバイス アクセス] ページ (「最新の認証を使用しないアプリからのアクセスを制御する」) で構成します。 [ブロック] を選択します。

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>ユーザーまたはユーザーのCloud App SecurityをOffice 365 Cloud App Security

リスクOffice 365 Cloud App Securityを評価し、疑わしいアクティビティに警告し、自動的にアクションを実行するには、この情報を使用します。 E5 Office 365が必要です。

または、Microsoft Cloud App Securityを含むすべてのクラウド アプリケーションに対するアクセス許可、包括的な制御、および強化された保護の後でも、Microsoft Cloud App Security を使用して、より深い可視性を得Office 365。

このソリューションでは EMS E5 プランをお勧めしますので、環境内の他の SaaS アプリケーションでこれを使用Cloud App Securityから開始することをお勧めします。 既定のポリシーと設定から開始します。

詳しくは、以下の資料を参照してください。

- [Cloud App Security を展開する](/cloud-app-security/getting-started-with-cloud-app-security)
- [Microsoft Cloud App Security の詳細情報](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Cloud App Security とは](/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security ダッシュボード](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>その他のリソース

以下の記事とガイドは、環境を保護するための追加のMicrosoft 365提供します。

- [政治キャンペーン、非営利団体](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) 、その他のアジャイル組織向け Microsoft セキュリティ ガイダンス (これらの推奨事項は、任意の環境、特にクラウド専用環境で使用できます)

- [ID とデバイスの推奨](microsoft-365-policies-configurations.md) セキュリティ ポリシーと構成 (これらの推奨事項には、FS 環境でのAD含まれます)
