---
title: セキュリティ強化のために、Microsoft 365 テナントを構成する
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
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
ms.openlocfilehash: b095d328a6582e93e79a2e6a76afe61ca59862cb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199347"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>セキュリティ強化のために、Microsoft 365 テナントを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

このトピックでは、テナント環境のセキュリティに影響を与えるテナント全体の設定に対する推奨構成Microsoft 365説明します。 セキュリティニーズには、多かれ少なかれセキュリティが必要になる場合があります。 これらの推奨事項を開始点として使用します。

## <a name="check-office-365-secure-score"></a>セキュリティOffice 365スコアを確認する

Office 365Secure Score は、通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てる。 まず、現在のスコアをメモします。 テナント全体の設定を調整すると、スコアが向上します。 目標は、最大スコアを達成するのではなく、ユーザーの生産性に悪影響を及ぼしない環境を保護する機会を認識する方法です。 「Microsoft [Secure Score」を参照してください](../defender/microsoft-secure-score.md)。

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで脅威管理ポリシーを調整する

このMicrosoft 365 Defenderには、環境を保護する機能が含まれています。 また、監視とアクションの実行に使用できるレポートとダッシュボードも含まれています。 一部の領域では、既定のポリシー構成が使用されます。 一部の領域には、既定のポリシーやルールが含まれます。 これらのポリシーについては、「**メール**& グループ &ルール脅威ポリシー」の下にアクセスして、より安全な環境の脅威管理設定 \>  \> を調整します。

<br>

****

|分野|既定のポリシー|推奨事項|
|---|---|---|
|**フィッシング対策**|はい|ここで説明するように、既定のフィッシング対策ポリシーを構成します。EOP と Defender for Office 365 でフィッシング対策[保護設定を構成します](protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[アプリ内のフィッシング対策Microsoft 365](set-up-anti-phishing-policies.md)</li><li>[Microsoft Defender のフィッシング対策ポリシー設定の推奨Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</li><li> [偽装に関する分析情報](impersonation-insight.md)</li><li>[EOP でのスプーフィング インテリジェンスの分析情報](learn-about-spoof-intelligence.md)</li><li>[テナントの許可/ブロックリストを管理します](tenant-allow-block-list.md)。</li></ul>|
|**マルウェア対策エンジン**|はい|「EOP でマルウェア対策保護設定を構成する」の説明に従って、既定のマルウェア対策ポリシー [を構成します](protect-against-threats.md#part-1---anti-malware-protection-in-eop)。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[マルウェア対策保護](anti-malware-protection.md)</li><li>[推奨されるマルウェア対策ポリシー設定](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</li><li>[マルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)</li></ul>|
|**Defender for Office 365 の安全な添付ファイル**|いいえ|「Microsoft [Defender](protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)for セーフ の添付ファイルの設定を構成し、セーフ 添付ファイルポリシーを作成する」の説明に従ってセーフ添付ファイルの設定をOffice 365。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[推奨セーフ添付ファイルの設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</li><li>[セーフMicrosoft Defender の添付ファイル (Office 365](safe-attachments.md)</li><li>[安全な添付ファイル機能のポリシーを設定する](set-up-safe-attachments-policies.md)</li><li>[SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)</li><li>[Microsoft 365 E5 の安全なドキュメント](safe-docs.md)</li></ul>|
|**セーフMicrosoft Defender for Office 365**|いいえ|「Microsoft Defender for セーフ の セーフ リンクのグローバル設定を構成し、セーフ リンク ポリシーを作成する」の説明に従って、「Microsoft Defender で セーフ リンクの設定を構成する」[をOffice 365。](protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365) <p> 詳しくは、以下の資料を参照してください。 <ul><li>[推奨セーフリンクの設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)</li><li>[安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)</li><li>[セーフMicrosoft Defender for Office 365](safe-links.md)</li><li>[Microsoft Defender の [リンク] セーフのグローバル設定を構成するOffice 365](configure-global-settings-for-safe-links.md)</li></ul>|
|**スパム対策 (メール フィルター)**|はい|「EOP でスパム対策保護設定を構成する」の説明に従って、既定のスパム対策ポリシー [を構成する](protect-against-threats.md#part-3---anti-spam-protection-in-eop) <p> 詳しくは、以下の資料を参照してください。 <ul><li>[推奨されるスパム対策ポリシー設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</li><li>[EOP でのスパム対策保護](anti-spam-protection.md)</li><li>[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)</li></ul>|
|***電子メール認証***|はい|電子メール認証では、DNS レコードを使用して、メッセージ ソースと送信者に関する電子メール メッセージに検証可能な情報を追加します。 Microsoft 365 (onmicrosoft.com) のメール認証を自動的に構成しますが、Microsoft 365管理者はカスタム ドメインの電子メール認証を構成することもできます。 3 つの認証方法が使用されます。 <ul><li>送信者ポリシー フレームワーク (または SPF)。</li><ul><li>セットアップについては、「スプーフィング[を防止するために、Microsoft 365 SPF をセットアップする」を参照してください](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</li></ul> <li>DomainKeys Identified Mail (DKIM)。</li><ul><li>[「DKIM を使用してカスタム ドメインから送信される送信メールを検証する」を参照してください](use-dkim-to-validate-outbound-email.md)。</li><li>DKIM を構成した後、ポータルで DKIM をMicrosoft 365 Defenderします。</li></ul><li>ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC)</li><ul><li>DMARC セットアップでは[、DMARC を使用してメールを検証](use-dmarc-to-validate-email.md)Microsoft 365。</li></ul></ul>|
|

> [!NOTE]
> SPF、ハイブリッド展開、およびトラブルシューティングの非標準展開の場合: Microsoft 365 がスプーフィングを防止するために Sender [Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)を使用する方法。

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>ダッシュボードとレポートをポータルでMicrosoft 365 Defenderする

環境の正常性の詳細については、これらのレポートとダッシュボードをご覧ください。 これらのレポートのデータは、組織がサービスを使用するOffice 365されます。 今のところ、監視およびアクションを実行できる機能について理解してください。

<br>

****

|ダッシュボード|説明|
|---|---|
|電子メール セキュリティ レポート|これらのレポートは、Exchange Online Protection。 詳細については、「電子メール セキュリティ[レポートをポータルで表示する」をMicrosoft 365 Defenderしてください](view-email-security-reports.md)。|
|レポートのOffice 365ディフェンダー|レポートは、レポートの Defender でのみOffice 365。 詳細については、「View [Defender for Office 365ポータル」をMicrosoft 365 Defenderしてください](view-reports-for-mdo.md)。|
|メール フロー レポートと分析情報|これらのレポートと分析情報は、Exchangeセンター (EAC) で利用できます。 詳細については、「メール フロー レポート [」および「Mail flow](/exchange/monitoring/mail-flow-reports/mail-flow-reports) [insights」を参照してください](/exchange/monitoring/mail-flow-insights/mail-flow-insights)。|
|[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)|テナントに対する攻撃を調査または発生している場合は、エクスプローラー (またはリアルタイムの検出) を使用して脅威を分析します。 エクスプローラー (およびリアルタイム検出レポート) には、時間の過ぎた攻撃の量が表示され、脅威ファミリ、攻撃者インフラストラクチャなどによってこのデータを分析できます。 [インシデント] リストに不審なメールをマークできます。|
|

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>テナント全体のExchange Onlineを構成する

推奨される追加の設定を次に示します。

<br>

****

|分野|推奨事項|
|---|---|
|**メール フロー ルール** (トランスポート ルールとも呼ばれる)|実行可能ファイルの種類をブロックし、マクロを含むOfficeファイルの種類をブロックすることで、ランサムウェアから保護するためのメール フロー ルールを追加します。 詳細については、「メール フロー ルール[を使用してメッセージの添付ファイル](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)を調Exchange Online。 <p> 以下の追加トピックを参照してください。 <ul><li>[ランサムウェアから保護する](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[マルウェアとランサムウェアの保護 (Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[ユーザーのランサムウェア攻撃から回復Office 365](recover-from-ransomware.md)</li></ul> <p> メール フロー ルールを作成して、外部ドメインへのメールの自動転送を防止します。 詳細については、「Secure [Score を使用したクライアント外部転送ルールの緩和」を参照してください](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。 <p> 詳細: メール[フロー ルール (トランスポート](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)ルール) Exchange Online|
|**先進認証**|モダン認証は、多要素認証 (MFA) を使用する前提条件です。 メールを含むクラウド リソースへのアクセスをセキュリティで保護するには、MFA をお勧めします。 <p> 以下のトピックを参照してください。 <ul><li>[Exchange Online での最新認証の有効化または無効化](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Businessオンライン: テナントで最新の認証を有効にする](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> 最新の認証は、2016 年のクライアント、Officeオンライン、および SharePointに対して既定でOneDrive for Business。 <p> 詳細: [2013 年および 2016 年Office 2016](../../enterprise/modern-auth-for-office-2013-and-2016.md)年のOffice認証のしくみ|
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

リスクOffice 365 Cloud App Securityを評価し、疑わしいアクティビティに警告し、自動的にアクションを実行するには、この情報を使用します。 計画Office 365 E5必要です。

または、Microsoft Cloud App Securityを含むすべてのクラウド アプリケーションに対するアクセス許可、包括的な制御、および強化された保護の後でも、Microsoft Cloud App Security を使用して、より深い可視性を得Office 365。

このソリューションでは EMS E5 プランをお勧めしますので、環境内の他の SaaS アプリケーションでこれを使用Cloud App Securityから開始することをお勧めします。 既定のポリシーと設定から開始します。

詳しくは、以下の資料を参照してください。

- [Cloud App Security を展開する](/cloud-app-security/getting-started-with-cloud-app-security)
- [Microsoft Cloud App Security の詳細情報](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Cloud App Security とは](/cloud-app-security/what-is-cloud-app-security)

![Cloud App Securityダッシュボード。](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>その他のリソース

以下の記事とガイドは、環境を保護するための追加のMicrosoft 365提供します。

- [政治キャンペーン、非営利団体](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) 、その他のアジャイル組織向け Microsoft セキュリティ ガイダンス (これらの推奨事項は、任意の環境、特にクラウド専用環境で使用できます)

- [ID とデバイスの推奨](microsoft-365-policies-configurations.md) セキュリティ ポリシーと構成 (これらの推奨事項には、FS 環境でのAD含まれます)
