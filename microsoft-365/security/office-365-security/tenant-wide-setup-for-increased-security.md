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
- admindeeplinkSPO
description: このトピックでは、Microsoft 365 環境のセキュリティに影響を与えるテナント全体の設定の推奨構成について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82e96b4b35d5095a6844618125ee49f1dba6ffd6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318524"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>セキュリティ強化のために、Microsoft 365 テナントを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

このトピックでは、Microsoft 365 環境のセキュリティに影響を与えるテナント全体の設定の推奨構成について説明します。 セキュリティニーズには、多かれ少なかれセキュリティが必要になる場合があります。 これらの推奨事項を開始点として使用します。

## <a name="check-office-365-secure-score"></a>365 Officeスコアを確認する

Office 365 Secure Score は、通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てる。 まず、現在のスコアをメモします。 テナント全体の設定を調整すると、スコアが向上します。 目標は、最大スコアを達成するのではなく、ユーザーの生産性に悪影響を及ぼしない環境を保護する機会を認識する方法です。 「 [Microsoft Secure Score」を参照してください](../defender/microsoft-secure-score.md)。

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで脅威管理ポリシーを調整する

Microsoft 365 Defender ポータルには、環境を保護する機能が含まれています。 また、監視とアクションの実行に使用できるレポートとダッシュボードも含まれています。 一部の領域では、既定のポリシー構成が使用されます。 一部の領域には、既定のポリシーやルールが含まれます。 これらのポリシーについては、「**Email & コラボレーション** \>  \> ポリシー」の&ルール脅威ポリシーを参照して、より安全な環境の脅威管理設定を調整します。

<br>

****

|分野|既定のポリシー|推奨事項|
|---|---|---|
|**フィッシング対策**|はい|「EOP と Defender for Office [365](protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)」の説明に従って、既定のフィッシング対策ポリシーを構成します。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[Microsoft 365 のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)</li><li>[Microsoft Defender で推奨されるフィッシング対策ポリシー設定 (Office 365)](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</li><li> [偽装に関する分析情報](impersonation-insight.md)</li><li>[EOP でのスプーフィング インテリジェンスの分析情報](learn-about-spoof-intelligence.md)</li><li>[テナント許可/ブロック一覧を管理します](tenant-allow-block-list.md)。</li></ul>|
|**マルウェア対策エンジン**|はい|「EOP でマルウェア対策保護設定を構成する」の説明に従って、既定のマルウェア対策ポリシー [を構成します](protect-against-threats.md#part-1---anti-malware-protection-in-eop)。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[マルウェア対策保護](anti-malware-protection.md)</li><li>[推奨されるマルウェア対策ポリシー設定](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</li><li>[マルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)</li></ul>|
|**Defender for Office 365 の安全な添付ファイル**|いいえ|「安全な添付ファイルのグローバル設定を構成し、安全な添付ファイルポリシーを作成する」の説明に従って、「 [Microsoft Defender for microsoft Defender for Office 365」を参照](protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)してください。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[推奨される安全な添付ファイルの設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</li><li>[Microsoft Defender の安全な添付ファイル for Office 365](safe-attachments.md)</li><li>[安全な添付ファイル機能のポリシーを設定する](set-up-safe-attachments-policies.md)</li><li>[SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)</li><li>[Microsoft 365 E5 の安全なドキュメント](safe-docs.md)</li></ul>|
|**Microsoft Defender のセーフ リンク for Office 365**|いいえ|セーフ リンクのグローバル設定を構成し、セーフ リンク ポリシーを作成します(「 [Configure Safe Links settings in Microsoft Defender for microsoft Defender for Office 365](protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)」を参照してください。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[安全なリンクの推奨設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)</li><li>[安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)</li><li>[Microsoft Defender のセーフ リンク for Office 365](safe-links.md)</li><li>[Microsoft Defender のセーフ リンクのグローバル設定を構成する (Office 365)](configure-global-settings-for-safe-links.md)</li></ul>|
|**スパム対策 (メール フィルター)**|はい|「EOP でスパム対策保護設定を構成する」の説明に従って、既定のスパム対策ポリシー [を構成する](protect-against-threats.md#part-3---anti-spam-protection-in-eop) <p> 詳しくは、以下の資料を参照してください。 <ul><li>[推奨されるスパム対策ポリシー設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</li><li>[EOP でのスパム対策保護](anti-spam-protection.md)</li><li>[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)</li></ul>|
|***電子メール認証***|はい|電子メール認証では、DNS レコードを使用して、メッセージ ソースと送信者に関する電子メール メッセージに検証可能な情報を追加します。 Microsoft 365 は既定のドメイン (onmicrosoft.com) の電子メール認証を自動的に構成しますが、Microsoft 365 管理者はカスタム ドメインの電子メール認証を構成することもできます。 3 つの認証方法が使用されます。 <ul><li>送信者ポリシー フレームワーク (または SPF)。</li><ul><li>セットアップについては、「スプーフィングを防止 [するために Microsoft 365 で SPF をセットアップする」を参照してください](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</li></ul> <li>DomainKeys Identified Mail (DKIM)。</li><ul><li>「 [DKIM を使用してカスタム ドメインから送信される送信メールを検証する」を参照してください](use-dkim-to-validate-outbound-email.md)。</li><li>DKIM を構成した後、Microsoft 365 Defender ポータルで有効にしてください。</li></ul><li>ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC)</li><ul><li>DMARC セットアップでは [、DMARC を使用して Microsoft 365 で電子メールを検証します](use-dmarc-to-validate-email.md)。</li></ul></ul>|
|

> [!NOTE]
> SPF、ハイブリッド展開、およびトラブルシューティングの非標準展開の場合: Microsoft 365 がスプーフィングを防止するために Sender [Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md) を使用する方法。

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでダッシュボードとレポートを表示する

環境の正常性の詳細については、これらのレポートとダッシュボードをご覧ください。 これらのレポートのデータは、組織が 365 サービスを使用Officeになります。 今のところ、監視およびアクションを実行できる機能について理解してください。

<br>

****

|ダッシュボード|説明|
|---|---|
|電子メール セキュリティ レポート|これらのレポートは、Exchange Online Protection で使用できます。 詳細については、「 [Microsoft 365 Defender ポータルで電子メール セキュリティ レポートを表示する」を参照してください](view-email-security-reports.md)。|
|365 Officeの Defender|レポートは、365 の Defender でのみOfficeできます。 詳細については、「 [View Defender for Office 365 Defender ポータル」を参照してください](view-reports-for-mdo.md)。|
|メール フロー レポートと分析情報|これらのレポートと分析情報は、Exchange 管理センター (EAC) で利用できます。 詳細については、「メール フロー レポート[」と「Mail flow insights](/exchange/monitoring/mail-flow-reports/mail-flow-reports)[」を参照してください](/exchange/monitoring/mail-flow-insights/mail-flow-insights)。|
|[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)|テナントに対する攻撃を調査または発生している場合は、エクスプローラー (またはリアルタイムの検出) を使用して脅威を分析します。 エクスプローラー (およびリアルタイム検出レポート) には、時間の過ぎた攻撃の量が表示され、脅威ファミリ、攻撃者インフラストラクチャなどによってこのデータを分析できます。 [インシデント] リストに不審なメールをマークできます。|
|

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>追加の Exchange Online テナント全体の設定を構成する

推奨される追加の設定を次に示します。

<br>

****

|分野|推奨事項|
|---|---|
|**メール フロー ルール** (トランスポート ルールとも呼ばれる)|実行可能ファイルの種類をブロックし、マクロを含むOfficeファイルの種類をブロックすることで、ランサムウェアから保護するためのメール フロー ルールを追加します。 詳細については、「メール フロー ルールを [使用して Exchange Online でメッセージの添付ファイルを検査する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。 <p> 以下の追加トピックを参照してください。 <ul><li>[ランサムウェアから保護する](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Microsoft 365 のマルウェアとランサムウェアの保護](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[365 でランサムウェア攻撃からOfficeする](recover-from-ransomware.md)</li></ul> <p> メール フロー ルールを作成して、外部ドメインへのメールの自動転送を防止します。 詳細については、「Secure [Score を使用したクライアント外部転送ルールの緩和」を参照してください](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。 <p> 詳細: [Exchange Online のメール フロー ルール (トランスポート ルール)](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**先進認証**|モダン認証は、多要素認証 (MFA) を使用する前提条件です。 メールを含むクラウド リソースへのアクセスをセキュリティで保護するには、MFA をお勧めします。 <p> 以下のトピックを参照してください。 <ul><li>[Exchange Online での最新認証の有効化または無効化](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online: モダン認証用にテナントを有効にする](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> 最新の認証は、2016 Office SharePoint Online、および OneDrive for Business に対して既定で有効になっています。 <p> 詳細: [2016 クライアント アプリと 2016 Office 2013およびOfficeの認証のしくみ](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>SharePoint 管理センターでテナント全体の共有ポリシーを構成する

ベースライン保護から始まる、高いレベルの保護で SharePoint チーム サイトを構成するための Microsoft の推奨事項。 詳細については、「 [SharePoint サイトとファイルのセキュリティ保護に関するポリシーの推奨事項」を参照してください](sharepoint-file-access-policies.md)。

ベースライン レベルで構成された SharePoint チーム サイトでは、匿名アクセス リンクを使用して外部ユーザーとファイルを共有できます。 この方法は、電子メールでファイルを送信する代わりにお勧めします。

ベースライン保護の目標をサポートするには、ここで推奨されるテナント全体の共有ポリシーを構成します。 個々のサイトの共有設定は、このテナント全体のポリシーよりも制限が厳しい場合がありますが、より制限的ではありません。

<br>

****

|分野|既定のポリシーを含む|推奨事項|
|---|---|---|
|**共有** (SharePoint Online および OneDrive for Business)|はい|外部共有は既定で有効になっています。 これらの設定をお勧めします。 <ul><li>認証された外部ユーザーへの共有と匿名アクセス リンクの使用を許可する (既定の設定)。</li><li>匿名アクセス リンクは、この数日間で期限切れになります。 必要に応じて、30 日などの数値を入力します。</li><li>既定のリンクの種類 - [内部] (組織内のユーザーのみ) を選択します。 匿名リンクを使用して共有するユーザーは、共有メニューからこのオプションを選択する必要があります。</li></ul> <p> 詳細: [外部共有の概要](/sharepoint/external-sharing-overview)|
|

SharePoint 管理センターと OneDrive for Business 管理センターには、同じ設定が含まれます。 どちらの管理センターの設定も両方に適用されます。

## <a name="configure-settings-in-azure-active-directory"></a>Azure Active Directory で設定を構成する

Azure Active Directory のこれら 2 つの領域にアクセスして、より安全な環境のためのテナント全体のセットアップを完了してください。

### <a name="configure-named-locations-under-conditional-access"></a>名前付き場所を構成する (条件付きアクセスの下で)

組織にセキュリティで保護されたネットワーク アクセスを持つオフィスが含まれる場合は、信頼できる IP アドレス範囲を名前付き場所として Azure Active Directory に追加します。 この機能は、サインイン リスク イベントで報告された誤検知の数を減らすのに役立ちます。

参照: [Azure Active Directory の名前付き場所](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>モダン認証をサポートしないアプリをブロックする

多要素認証には、最新の認証をサポートするアプリが必要です。 最新の認証をサポートしていないアプリは、条件付きアクセス ルールを使用してブロックできません。

セキュリティで保護された環境では、最新の認証をサポートしていないアプリの認証を無効にしてください。 これを Azure Active Directory で行うには、近日公開予定のコントロールを使用します。

その間に、SharePoint Online および OneDrive for Business でこれを実行するには、次のいずれかの方法を使用します。

- PowerShell を使用する場合は、「 [モダン認証を使用しないアプリをブロックする」を参照してください](/mem/intune/protect/app-modern-authentication-block)。
- "デバイス アクセス" ページの <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint</a> 管理センターでこれを構成します。"最新の認証を使用しないアプリからのアクセスを制御する"。 [ブロック] を選択します。

## <a name="get-started-with-defender-for-cloud-apps-or-office-365-cloud-app-security"></a>Defender for Cloud Apps または 365 Cloud App Security Officeの使用を開始する

365 Office 365 Cloud App Security を使用して、リスクを評価し、疑わしいアクティビティに警告し、自動的にアクションを実行します。 365 Office 365 E5 プランが必要です。

または、Microsoft Defender for Cloud Apps を使用して、アクセスが許可された後でもより深い可視性を得たり、包括的な制御を行い、Office 365 を含むすべてのクラウド アプリケーションの保護を強化したりします。

このソリューションでは EMS E5 プランをお勧めしますので、環境内の他の SaaS アプリケーションで使用できるよう、Defender for Cloud Apps から開始することをお勧めします。 既定のポリシーと設定から開始します。

詳しくは、以下の資料を参照してください。

- [Defender for Cloud Apps の展開](/cloud-app-security/getting-started-with-cloud-app-security)
- [Microsoft Defender for Cloud Apps の詳細](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Defender for Cloud Apps とは](/cloud-app-security/what-is-cloud-app-security)

![Defender for Cloud Apps ダッシュボード。](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>その他のリソース

以下の記事とガイドでは、Microsoft 365 環境をセキュリティ保護するための追加の前付き情報を提供します。

- [政治キャンペーン、非営利団体](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) 、その他のアジャイル組織向け Microsoft セキュリティ ガイダンス (これらの推奨事項は、任意の環境、特にクラウド専用環境で使用できます)

- [ID とデバイスの推奨](microsoft-365-policies-configurations.md) セキュリティ ポリシーと構成 (これらの推奨事項には、FS 環境のAD含まれます)
