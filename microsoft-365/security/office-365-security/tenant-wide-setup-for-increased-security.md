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
ms.openlocfilehash: efcc468dc9b6a41af79ecf2f22a6ad58a410e08f
ms.sourcegitcommit: a46532bb422ee51331f478ff50cc5444586bf6a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51650328"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>セキュリティ強化のために、Office 365 テナントを構成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

このトピックでは、Microsoft 365 環境のセキュリティに影響を与えるテナント全体の設定の推奨構成について説明します。 セキュリティニーズには、多かれ少なかれセキュリティが必要になる場合があります。 これらの推奨事項を開始点として使用します。

## <a name="check-office-365-secure-score"></a>365 Officeスコアを確認する

Office 365 Secure Score は、通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てる。 まず、現在のスコアをメモします。 テナント全体の設定を調整すると、スコアが向上します。 目標は、最大スコアを達成するのではなく、ユーザーの生産性に悪影響を及ぼしない環境を保護する機会を認識する方法です。 「Microsoft [Secure Score」を参照してください](../defender/microsoft-secure-score.md)。

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターで脅威管理ポリシーを調整する

Microsoft 365 セキュリティ センターには、環境を保護する機能が含まれています。 また、監視とアクションの実行に使用できるレポートとダッシュボードも含まれています。 一部の領域では、既定のポリシー構成が使用されます。 一部の領域には、既定のポリシーやルールが含まれます。 脅威管理の下にあるこれらのポリシーにアクセスして、より安全な環境の脅威管理設定を調整します。

****

|分野|既定のポリシーを含む|推奨事項|
|---|---|---|
|**フィッシング対策**|はい|カスタム ドメインがある場合は、CEO などの最も価値のあるユーザーのメール アカウントを保護し、ドメインを保護するために、既定のフィッシング対策ポリシーを構成します。 <p> [Office 365](set-up-anti-phishing-policies.md)のフィッシング対策ポリシーを確認し[、「EOP](configure-anti-phishing-policies-eop.md)でフィッシング対策ポリシーを構成する」または「Microsoft Defender for Office [365](configure-atp-anti-phishing-policies.md)でフィッシング対策ポリシーを構成する」を参照してください。|
|**マルウェア対策エンジン**|はい| 既定のポリシーを編集します。 <ul><li>共通の添付ファイルの種類フィルター: [オン] を選択します。</li></ul> <p> カスタム マルウェア フィルター ポリシーを作成し、組織内の指定したユーザー、グループ、またはドメインに適用することもできます。 <p> 詳しくは、以下の資料を参照してください。 <ul><li>[マルウェア対策保護](anti-malware-protection.md)</li><li>[マルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)</li></ul>|
|**Microsoft Defender の安全な添付ファイル for Office 365**|いいえ|[安全な添付ファイル] のメイン ページで、[グローバル設定] **をクリックし** 、次の設定をオンにします。 <ul><li>**SharePoint、OneDrive、Microsoft Teams 用の Microsoft Defender for Office 365 を有効にする**</li></ul> <p> 次の設定で安全な添付ファイル ポリシーを作成します。 <ul><li> **[ブロック**]: 不明 **なマルウェア応答** として [ブロック] を選択します。</li><li>**リダイレクトを有効** にする: このボックスをオンにして、管理者アカウントや検疫アカウントなどの電子メール アドレスを入力します。</li><li>**添付ファイルのマルウェア スキャンがタイム アウト** またはエラーが発生した場合は、上記の選択を適用します。このボックスをオンにします。</li><li>**_適用:_***受信者ドメインがドメイン** \> を選択します。</li></ul> <p> 詳細: [SharePoint、OneDrive、Microsoft Teams](mdo-for-spo-odb-and-teams.md) の安全な添付ファイルと安全な添付ファイル [ポリシーの設定](set-up-safe-attachments-policies.md)|
|**Microsoft Defender for Office 365 の安全なリンク**|はい|[セーフ リンク] のメイン ページで、[グローバル設定] **をクリックします**。 <ul><li>**[セーフ リンクを使用する: Office 365 アプリケーション**: この設定が有効になっていることを確認します。</li><li>**ユーザーが [安全なリンク] をクリック** しても追跡しない : この設定をオフにすると、ユーザーのクリックを追跡できます。</li></ul> <p> 次の設定で安全なリンク ポリシーを作成します。 <ul><li>**メッセージ内の不明な潜在的に悪意** のある URL のアクションを選択します。この設定が [オン] である必要 **があります**。</li><li>**Microsoft Teams 内の不明な** URL または潜在的に悪意のある URL のアクションを選択します。この設定が [オン] に設定されているのを確認 **します**。</li><li>**ファイルを指す疑わしいリンク** やリンクに対してリアルタイムの URL スキャンを適用する: このボックスをオンにします。</li><li>**メッセージを配信する前に URL** のスキャンが完了するのを待ちます。このボックスをオンにします。</li><li>**組織内で送信された電子メール メッセージに安全なリンクを適用** する : このボックスをオンにします。</li><li>**ユーザーに元の URL へのクリックを** 許可しない: このボックスをオンにします。</li><li>**適用先**: **受信者ドメインがドメイン** \> を選択します。</li></ul> <p> 詳細: [安全なリンク ポリシーを設定します](set-up-safe-links-policies.md)。|
|**スパム対策 (メール フィルター)**|はい| 何を見守る: <ul><li>スパムが多すぎます - カスタム設定を選択し、既定のスパム フィルター ポリシーを編集します。</li><li>スプーフィング インテリジェンス : ドメインをスプーフィングしている送信者を確認します。 これらの送信者をブロックまたは許可します。</li></ul> <p> 詳細: [Microsoft 365 Email Anti-Spam Protection](anti-spam-protection.md).|
|***電子メール認証***|はい|電子メール認証では、ドメイン ネーム システム (DNS) を使用して、電子メールの送信者に関する電子メール メッセージに検証可能な情報を追加します。 Microsoft 365 は既定のドメイン (onmicrosoft.com) の電子メール認証を設定しますが、Microsoft 365 管理者はカスタム ドメインに電子メール認証を使用できます。 3 つの認証方法が使用されます。 <ul><li>送信者ポリシー フレームワーク (または SPF)。</li><ul><li>セットアップについては、「スプーフィングを防止するために [Microsoft 365 で SPF をセットアップする」を参照してください](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</li></ul> <li>DomainKeys Identified Mail (DKIM)。</li><ul><li>[「DKIM を使用してカスタム ドメインから送信される送信メールを検証する」を参照してください](use-dkim-to-validate-outbound-email.md)。</li><li>DKIM を構成した後、セキュリティ センターで有効にしてください。</li></ul><li>ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC)</li><ul><li>DMARC セットアップでは [、DMARC を使用して Microsoft 365 で電子メールを検証します](use-dmarc-to-validate-email.md)。</li></ul></ul>|
|

> [!NOTE]
> SPF、ハイブリッド展開、およびトラブルシューティングの非標準展開の場合: Microsoft [365](how-office-365-uses-spf-to-prevent-spoofing.md)がスプーフィングを防止するために Sender Policy Framework (SPF) を使用する方法。

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>セキュリティ センターとコンプライアンス センターでダッシュボードとレポートを表示する

環境の正常性の詳細については、これらのレポートとダッシュボードをご覧ください。 これらのレポートのデータは、組織が 365 サービスを使用するOfficeになります。 今のところ、監視およびアクションを実行できる機能について理解してください。 詳細については [、「Microsoft 365 セキュリティ](../../compliance/reports-in-security-and-compliance.md)/コンプライアンス センターのレポート」を参照してください。

****

|ダッシュボード|説明|
|---|---|
|[脅威管理ダッシュボード](security-dashboard.md)|セキュリティセンターの [脅威管理] セクションで、このダッシュボードを使用して、既に処理されている脅威を確認し、ビジネスをセキュリティで保護するために既に行っている脅威の調査と対応の機能についてビジネス意思決定者に報告するための便利なツールとして使用します。|
|[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)|これは、セキュリティ センターの **[脅威の管理** ] セクションにも表示されます。 テナントに対する攻撃を調査または発生している場合は、エクスプローラー (またはリアルタイムの検出) を使用して脅威を分析します。 エクスプローラー (およびリアルタイム検出レポート) には、時間の過ぎた攻撃の量が表示され、脅威ファミリ、攻撃者インフラストラクチャなどによってこのデータを分析できます。 [インシデント] リストに不審なメールをマークできます。|
|レポート - ダッシュボード|セキュリティ センターの **[レポート** ] セクションで、SharePoint Online 組織および Exchange Online 組織の監査レポートを表示します。 [レポートの表示] ページから Azure Active Directory (Azure AD) ユーザー サインイン レポート、ユーザー アクティビティ レポート、Azure AD 監査ログに **アクセス** することもできます。|
|

![セキュリティ センター ダッシュボード](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>追加の Exchange Online テナント全体の設定を構成する

Exchange 管理センターのセキュリティと保護のためのコントロールの多くは、セキュリティ センターにも含まれています。 両方の場所でこれらを構成する必要はない。 推奨される追加の設定を次に示します。

****

|分野|既定のポリシーを含む|推奨事項|
|---|---|---|
|**メール フロー** (メール フロー ルール (トランスポート ルールとも呼ばれる)|いいえ|実行可能ファイルの種類をブロックし、マクロを含むOfficeファイルの種類をブロックすることで、ランサムウェアから保護するためのメール フロー ルールを追加します。 詳細については、「メール フロー ルールを使用して Exchange Online で [メッセージ添付ファイルを検査する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。 <p> 以下の追加トピックを参照してください。 <ul><li>[ランサムウェアから保護する](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Microsoft 365 のマルウェアとランサムウェアの保護](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[365 でランサムウェア攻撃からOfficeする](recover-from-ransomware.md)</li></ul> <p> メール フロー ルールを作成して、外部ドメインへのメールの自動転送を防止します。 詳細については、「Secure [Score を使用したクライアント外部転送ルールの緩和」を参照してください](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。 <p> 詳細: [Exchange Online のメール フロー ルール (トランスポート ルール)](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**モダン認証を有効にする**|いいえ|モダン認証は、多要素認証 (MFA) を使用する前提条件です。 メールを含むクラウド リソースへのアクセスをセキュリティで保護するには、MFA をお勧めします。 <p> 以下のトピックを参照してください。 <ul><li>[Exchange Online での最新認証の有効化または無効化](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online: モダン認証用にテナントを有効にする](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> モダン認証は、2016 クライアント、SharePoint Online、および OneDrive for Business Office既定で有効になっています。 <p> 詳細: [2016 クライアント アプリと 2016](../../enterprise/modern-auth-for-office-2013-and-2016.md) Office 2013およびOffice認証のしくみ|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>SharePoint 管理センターでテナント全体の共有ポリシーを構成する

ベースライン保護から始まる、高いレベルの保護で SharePoint チーム サイトを構成するための Microsoft の推奨事項。 詳細については [、「SharePoint サイトとファイルのセキュリティ保護に関するポリシーの推奨事項」を参照してください](sharepoint-file-access-policies.md)。

ベースライン レベルで構成された SharePoint チーム サイトでは、匿名アクセス リンクを使用して外部ユーザーとファイルを共有できます。 この方法は、電子メールでファイルを送信する代わりにお勧めします。

ベースライン保護の目標をサポートするには、ここで推奨されるテナント全体の共有ポリシーを構成します。 個々のサイトの共有設定は、このテナント全体のポリシーよりも制限が厳しい場合がありますが、より制限的ではありません。

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

- PowerShell を使用して、 [モダン認証 (ADAL) を使用しないアプリをブロックするを参照してください](/mem/intune/protect/app-modern-authentication-block)。

- "デバイス アクセス" ページの SharePoint 管理センターでこれを構成します。"最新の認証を使用しないアプリからのアクセスを制御する"。 [ブロック] を選択します。

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Cloud App Security または 365 Cloud App Security Officeを開始する

365 Office 365 Cloud App Security を使用して、リスクを評価し、疑わしいアクティビティに警告し、自動的にアクションを実行します。 365 Office 365 E5 プランが必要です。

または、Microsoft Cloud App Security を使用して、アクセスが許可された後でも、より深い可視性を取得し、包括的な制御を行い、Office 365 を含むすべてのクラウド アプリケーションの保護を強化します。

このソリューションでは EMS E5 プランをお勧めしますので、環境内の他の SaaS アプリケーションでこれを使用できるよう、クラウド アプリ セキュリティから開始することをお勧めします。 既定のポリシーと設定から開始します。

詳しくは、以下の資料を参照してください。

- [Cloud App Security を展開する](/cloud-app-security/getting-started-with-cloud-app-security)

- [Microsoft Cloud App Security の詳細情報](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Cloud App Security とは](/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security ダッシュボード](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>その他のリソース

以下の記事とガイドでは、Microsoft 365 環境をセキュリティ保護するための追加の前付き情報を提供します。

- [政治キャンペーン、非営利団体](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) 、その他のアジャイル組織向け Microsoft セキュリティ ガイダンス (これらの推奨事項は、任意の環境、特にクラウド専用環境で使用できます)

- [ID とデバイスの推奨](microsoft-365-policies-configurations.md) セキュリティ ポリシーと構成 (これらの推奨事項には、FS 環境でのAD含まれます)