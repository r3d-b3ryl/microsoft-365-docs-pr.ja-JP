---
title: セキュリティ強化のために、Microsoft 365 テナントを構成する
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 04/06/2022
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
- admindeeplinkSPO
description: このトピックでは、Microsoft 365環境のセキュリティに影響を与えるテナント全体の設定に推奨される構成について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 30b46bd541f233430506766eabc2d667fad52c22
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65097296"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>セキュリティ強化のために、Microsoft 365 テナントを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

このトピックでは、Microsoft 365環境のセキュリティに影響を与えるテナント全体の設定に推奨される構成について説明します。 セキュリティ ニーズには、多かれ少なかれセキュリティが必要な場合があります。 これらの推奨事項を開始点として使用します。

## <a name="check-office-365-secure-score"></a>セキュリティスコアOffice 365確認する

セキュリティスコアOffice 365、通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てます。 まず、現在のスコアを書き留めます。 テナント全体の設定を調整すると、スコアが向上します。 目標は、最大スコアを達成することではなく、ユーザーの生産性に悪影響を及ぼさない環境を保護する機会を認識することです。 [Microsoft セキュリティ スコアを](../defender/microsoft-secure-score.md)参照してください。

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで脅威管理ポリシーを調整する

Microsoft 365 Defender ポータルには、環境を保護する機能が含まれています。 また、監視とアクションの実行に使用できるレポートとダッシュボードも含まれています。 一部の領域には、既定のポリシー構成が付属しています。 一部の領域には、既定のポリシーやルールが含まれていません。 **電子メール & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** の下にあるこれらのポリシーにアクセスして、より安全な環境の脅威管理設定を調整します。

|分野|既定のポリシー?|推奨事項|
|---|---|---|
|**フィッシング詐欺対策**|はい|「[EOP とDefender for Office 365でフィッシング対策の保護設定を構成する」で説明するように、既定のフィッシング対策ポリシーを構成](protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)します。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[Microsoft 365 のフィッシング詐欺対策ポリシー](set-up-anti-phishing-policies.md)</li><li>[Microsoft Defender for Office 365で推奨されるフィッシング対策ポリシー設定](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</li><li> [偽装に関する分析情報](impersonation-insight.md)</li><li>詳細については、「[EOP のスプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)」を参照してください。</li><li>[テナント許可/ブロック リストを管理します](tenant-allow-block-list.md)。</li></ul>|
|**マルウェア対策エンジン**|はい|「EOP でマルウェア対策の保護設定を構成する」で説明するように [、既定のマルウェア対策ポリシーを構成](protect-against-threats.md#part-1---anti-malware-protection-in-eop)します。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[マルウェア対策保護](anti-malware-protection.md)</li><li>[推奨されるマルウェア対策ポリシー設定](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</li><li>[マルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)</li></ul>|
|**Defender for Office 365 の安全な添付ファイル**|なし|セーフ添付ファイルのグローバル設定を構成し、セーフ添付ファイル ポリシーを作成します。「Microsoft Defender for Office 365[でセーフ添付ファイルの設定を構成](protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)する」を参照してください。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[推奨セーフ添付ファイルの設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</li><li>[Microsoft Defender for Office 365で添付ファイルをセーフする](safe-attachments.md)</li><li>[安全な添付ファイル機能のポリシーを設定する](set-up-safe-attachments-policies.md)</li><li>[SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)</li><li>[Microsoft 365 E5 の安全なドキュメント](safe-docs.md)</li></ul>|
|**Microsoft Defender for Office 365 の安全なリンク**|いいえ|セーフ リンクのグローバル設定を構成し、次の説明に従って セーフ リンク ポリシーを作成します:[Microsoft Defender for Office 365でリンク設定セーフ構成](protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)します。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[推奨セーフリンク設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)</li><li>[安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)</li><li>[Microsoft Defender for Office 365 の安全なリンク](safe-links.md)</li><li>[Microsoft Defender for Office 365で セーフ リンクのグローバル設定を構成する](configure-global-settings-for-safe-links.md)</li></ul>|
|**スパム対策 (メール フィルター)**|はい|「EOP でスパム対策の設定を構成する」で説明するように既定[のスパム対策ポリシーを構成](protect-against-threats.md#part-3---anti-spam-protection-in-eop)する <p> 詳しくは、以下の資料を参照してください。 <ul><li>[推奨されるスパム対策ポリシー設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</li><li>[EOP のスパム対策保護](anti-spam-protection.md)</li><li>[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)</li></ul>|
|***電子メール認証***|はい|電子メール認証では、DNS レコードを使用して、メッセージの送信元と送信者に関する検証可能な情報を電子メール メッセージに追加します。 Microsoft 365は既定のドメイン (onmicrosoft.com) の電子メール認証を自動的に構成しますが、Microsoft 365管理者はカスタム ドメインの電子メール認証を構成することもできます。 次の 3 つの認証方法が使用されます。 <ul><li>Sender Policy Framework (または SPF)。</li><ul><li>セットアップについては、「[Microsoft 365で SPF を設定してスプーフィングを防止する」を](set-up-spf-in-office-365-to-help-prevent-spoofing.md)参照してください。</li></ul> <li>DomainKeys によって識別されたメール (DKIM)。</li><ul><li>[カスタム ドメインから送信された送信メールを検証するには、DKIM を使用する方法に関するページを参照してください](use-dkim-to-validate-outbound-email.md)。</li><li>DKIM を構成したら、Microsoft 365 Defender ポータルで有効にします。</li></ul><li>ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC)。</li><ul><li>DMARC セットアップの場合は、[DMARC を使用してMicrosoft 365で電子メールを検証](use-dmarc-to-validate-email.md)します。</li></ul></ul>|

> [!NOTE]
> SPF、ハイブリッド展開、およびトラブルシューティングの標準以外の展開の場合: [Microsoft 365送信者ポリシー フレームワーク (SPF) を使用してスプーフィングを防ぐ方法](how-office-365-uses-spf-to-prevent-spoofing.md)。

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでダッシュボードとレポートを表示する

環境の正常性の詳細については、これらのレポートとダッシュボードにアクセスしてください。 組織がOffice 365サービスを使用すると、これらのレポートのデータが豊富になります。 現時点では、監視してアクションを実行できることについて理解してください。

|ダッシュボード|説明|
|---|---|
|電子メール セキュリティ レポート|これらのレポートは、Exchange Online Protectionで使用できます。 詳細については、「[Microsoft 365 Defender ポータルで電子メール セキュリティ レポートを表示する](view-email-security-reports.md)」を参照してください。|
|レポートのDefender for Office 365|レポートはDefender for Office 365でのみ使用できます。 詳細については、「[Microsoft 365 Defender ポータルでレポートDefender for Office 365表示する」を参照してください](view-reports-for-mdo.md)。|
|メール フロー レポートと分析情報|これらのレポートと分析情報は、Exchange管理センター (EAC) で入手できます。 詳細については、「 [メール フロー レポート](/exchange/monitoring/mail-flow-reports/mail-flow-reports) 」と「 [メール フローの分析情報」を](/exchange/monitoring/mail-flow-insights/mail-flow-insights)参照してください。|
|[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)|テナントに対する攻撃を調査または発生している場合は、エクスプローラー (またはリアルタイム検出) を使用して脅威を分析します。 エクスプローラー (およびリアルタイム検出レポート) では、時間の経過に伴う攻撃の量が表示され、脅威ファミリ、攻撃者インフラストラクチャなどによってこのデータを分析できます。 [インシデント] ボックスの一覧に不審なメールをマークすることもできます。|

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>テナント全体の追加設定Exchange Online構成する

推奨されるその他の設定をいくつか次に示します。

|分野|推奨事項|
|---|---|
|**メール フロー ルール** (トランスポート ルールとも呼ばれます)|実行可能ファイルの種類とマクロを含むOfficeファイルの種類をブロックすることで、ランサムウェアから保護するために役立つメール フロー ルールを追加します。 詳細については、「[メール フロー ルールを使用してExchange Onlineのメッセージの添付ファイルを検査する](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)」を参照してください。 <p> 次の追加トピックを参照してください。 <ul><li>[ランサムウェアから保護する](../../admin/security-and-compliance/secure-your-business-data.md)</li><li>[Microsoft 365のマルウェアとランサムウェアの保護](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Office 365でのランサムウェア攻撃から回復する](recover-from-ransomware.md)</li></ul> <p> 外部ドメインへの電子メールの自動転送を防止するメール フロー ルールを作成します。 詳細については、「 [セキュリティで保護されたスコアを使用したクライアント外部転送ルールの軽減](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)」を参照してください。 <p> 詳細情報: [Exchange Onlineのメール フロー ルール (トランスポート ルール)](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**先進認証**|先進認証は、多要素認証 (MFA) を使用するための前提条件です。 MFA は、電子メールを含むクラウド リソースへのアクセスをセキュリティで保護するために推奨されます。 <p> 次のトピックを参照してください。 <ul><li>[Exchange Online での最新認証の有効化または無効化](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online: テナントで最新の認証を有効にする](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> 先進認証は、Office 2016 クライアント、SharePoint Online、およびOneDrive for Businessに対して既定で有効になっています。 <p> 詳細: [Office 2013 および Office 2016 クライアント アプリの先進認証のしくみ](../../enterprise/modern-auth-for-office-2013-and-2016.md)|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>管理センターでテナント全体の共有ポリシー SharePoint構成する

ベースライン保護から始めて、保護レベルを上げるSharePointチーム サイトを構成するための Microsoft の推奨事項。 詳細については、「[SharePoint サイトとファイルをセキュリティで保護するためのポリシーに関する推奨事項](sharepoint-file-access-policies.md)」を参照してください。

ベースライン レベルで構成されたチーム サイトSharePoint、匿名アクセス リンクを使用して外部ユーザーとファイルを共有できます。 この方法は、電子メールでファイルを送信する代わりに推奨されます。

ベースライン保護の目標をサポートするには、ここで推奨されているようにテナント全体の共有ポリシーを構成します。 個々のサイトの共有設定は、このテナント全体のポリシーよりも制限が厳しい場合がありますが、より許容されるわけではありません。

|分野|既定のポリシーを含む|推奨事項|
|---|---|---|
|**共有** (オンラインとOneDrive for Business SharePoint)|はい|外部共有は既定で有効になっています。 次の設定をお勧めします。 <ul><li>認証された外部ユーザーへの共有と匿名アクセス リンクの使用を許可します (既定の設定)。</li><li>匿名アクセス リンクは、この多くの日で期限切れになります。 必要に応じて、30 日間など、数値を入力します。</li><li>既定のリンクの種類 - [内部] (組織内のユーザーのみ) を選択します。 匿名リンクを使用して共有するユーザーは、共有メニューからこのオプションを選択する必要があります。</li></ul> <p> 詳細情報: [外部共有の概要](/sharepoint/external-sharing-overview)|

管理センターと管理センター OneDrive for Business SharePoint同じ設定が含まれています。 どちらの管理センターの設定も両方に適用されます。

## <a name="configure-settings-in-azure-active-directory"></a>Azure Active Directoryで設定を構成する

Azure Active Directoryのこれら 2 つの領域にアクセスして、より安全な環境のためにテナント全体のセットアップを完了してください。

### <a name="configure-named-locations-under-conditional-access"></a>名前付き場所を構成する (条件付きアクセスの下)

組織にセキュリティで保護されたネットワーク アクセスを持つオフィスが含まれている場合は、信頼された IP アドレス範囲を名前付き場所としてAzure Active Directoryに追加します。 この機能は、サインイン リスク イベントに対して報告された誤検知の数を減らすのに役立ちます。

参照: [Azure Active Directoryの名前付き場所](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>先進認証をサポートしていないアプリをブロックする

多要素認証には、最新の認証をサポートするアプリが必要です。 モダン認証をサポートしていないアプリは、条件付きアクセス規則を使用してブロックできません。

セキュリティで保護された環境の場合は、最新の認証をサポートしていないアプリの認証を必ず無効にします。 これは、近日公開予定のコントロールを使用してAzure Active Directoryで行うことができます。

それまでの間は、次のいずれかの方法を使用して、SharePoint Online とOneDrive for Businessに対してこれを実現します。

- PowerShell を使用する方法については、「 [先進認証を使用しないアプリをブロックする](/mem/intune/protect/app-modern-authentication-block)」を参照してください。
- これを構成するには、<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint管理センター</a>の [デバイス アクセス] ページの [モダン認証を使用しないアプリからのアクセスを制御する] ページです。 [ブロック] を選択します。

## <a name="get-started-with-defender-for-cloud-apps-or-office-365-cloud-app-security"></a>Defender for Cloud アプリまたはOffice 365 Cloud App Securityの概要

Office 365 Cloud App Securityを使用してリスクを評価し、疑わしいアクティビティをアラートし、自動的にアクションを実行します。 プランOffice 365 E5必要です。

または、Microsoft Defender for Cloud Appsを使用して、アクセスが許可された後でも可視性を高め、包括的な制御を行い、Office 365を含むすべてのクラウド アプリケーションの保護を強化します。

このソリューションでは EMS E5 プランが推奨されるため、環境内の他の SaaS アプリケーションでこれを使用できるように、Defender for Cloud アプリから開始することをお勧めします。 既定のポリシーと設定から始めます。

詳しくは、以下の資料を参照してください。

- [Defender for Cloud Apps の展開](/cloud-app-security/getting-started-with-cloud-app-security)
- [Microsoft Defender for Cloud Apps の詳細情報](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Defender for Cloud Apps とは](/cloud-app-security/what-is-cloud-app-security)

:::image type="content" source="../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png" alt-text="Defender for Cloud アプリ ダッシュボード" lightbox="../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png":::

## <a name="additional-resources"></a>その他のリソース

これらの記事とガイドでは、Microsoft 365環境をセキュリティで保護するための追加の規範的な情報を提供します。

- [政府機関、非営利団体、その他のアジャイル組織向けの Microsoft セキュリティ ガイダンス](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) (これらの推奨事項は、任意の環境 (特にクラウド専用環境) で使用できます)

- [ID とデバイスの推奨されるセキュリティ ポリシーと構成](microsoft-365-policies-configurations.md) (これらの推奨事項には、AD FS 環境のヘルプが含まれます)
