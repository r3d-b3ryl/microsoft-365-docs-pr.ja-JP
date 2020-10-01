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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: このトピックでは、Microsoft 365 環境のセキュリティに影響を与えるテナント全体の設定に推奨される構成について手順を追って説明します。
ms.openlocfilehash: 9e36c85b74a237a8b14904839aad55ac676dcaf4
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326927"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>セキュリティ強化のために、Office 365 テナントを構成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


このトピックでは、Microsoft 365 環境のセキュリティに影響を与えるテナント全体の設定に推奨される構成について手順を追って説明します。 セキュリティのニーズによっては、より多くのセキュリティを必要とする場合があります。 これらの推奨事項を出発点として使用します。

## <a name="check-office-365-secure-score"></a>Office 365 のセキュリティで保護されたスコアを確認する

Office 365 のセキュリティで保護されたスコアは、定期的なアクティビティおよびセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てます。 最初に、現在のスコアをメモしておきます。 テナント全体の設定を調整すると、スコアが増加します。 目標は最大スコアを達成することではなく、ユーザーの生産性に悪影響を及ぼすことがない環境を保護する機会に注意してください。 「 [Microsoft セキュリティスコア](../mtp/microsoft-secure-score.md)」を参照してください。

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティセンターで脅威管理ポリシーを調整する

Microsoft 365 セキュリティセンターには、環境を保護する機能が含まれています。 また、レポートとダッシュボードを使用して、監視してアクションを実行することもできます。 既定のポリシー構成には、いくつかの領域があります。 一部の領域には、既定のポリシーやルールは含まれません。 脅威管理の設定を調整して、より安全な環境を構成するには、次のポリシーにアクセスしてください。

****

|分野|既定のポリシーが含まれています|推奨事項|
|---|---|---|
|**フィッシング対策**|はい|カスタムドメインがある場合は、既定のフィッシング対策ポリシーを構成して、CEO などの最も重要なユーザーの電子メールアカウントを保護し、ドメインを保護します。 [Office 365 のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)を確認し、「configure フィッシング対策ポリシーを[EOP に構成する](configure-anti-phishing-policies-eop.md)か、「 [Office 365 で ATP のフィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)」を参照してください。|
|**マルウェア対策エンジン**|はい| 既定のポリシーを編集します。 <br/> &ensp;&ensp;* 一般的な添付ファイルの種類のフィルター— [オン] <br/><br/> また、カスタムマルウェアフィルターポリシーを作成して、それを組織内の特定のユーザー、グループ、またはドメインに適用することもできます。 <br/><br/> 詳しくは、以下の資料を参照してください。 <br/> &ensp;&ensp;* [マルウェア対策保護](anti-malware-protection.md) <br/> &ensp;&ensp;* [マルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)|
|**Office 365 ATP の安全な添付ファイル**|いいえ|安全な添付ファイルのメインページで、[ **グローバル設定** ] をクリックし、この設定をオンにします。 <br/> &ensp;&ensp;**SharePoint、OneDrive、Microsoft Teams の ATP を有効にする** <br/><br/> 次の設定を使用して、安全な添付ファイルポリシーを作成します。 <br/> &ensp;&ensp;* **ブロック**: 不明なマルウェア応答として [ **ブロック** ] を選択します。 <br/> &ensp;&ensp;* **リダイレクトを有効にする**: このボックスをオンにして、管理者や検疫アカウントなどの電子メールアドレスを入力します。 <br/> &ensp;&ensp;* **マルウェアスキャンによる添付ファイルのタイムアウトまたはエラーが発生した場合は、上記の選択を適用**します。このチェックボックスをオンにします。 <br/> &ensp;&ensp;* **適用先**: **受信者ドメインは、** \> ドメインを選択します。 <br/><br/> 詳細情報: [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)を行い、[安全な添付ファイルポリシーを設定](set-up-atp-safe-attachments-policies.md)する|
|**Office 365 ATP の安全なリンク**|はい|[安全なリンク] のメインページで、[ **グローバル設定**] をクリックします。 <br/> &ensp;&ensp;* **安全なリンクの使用: Office 365 applications**: この設定が有効になっていることを確認します。 <br/> &ensp;&ensp;* **ユーザーが [安全なリンク] をクリックしたときに追跡しない**: この設定をオフにして、ユーザーのクリックを追跡します。<br/><br/>次の設定を使用して、安全なリンクポリシーを作成します。 <br/> &ensp;&ensp;* **[メッセージ内の不明な潜在的な悪意のある url に対するアクション]**: この設定が **オンに**なっていることを確認します。 <br/> &ensp;&ensp;* **Microsoft Teams 内の不明または悪意のある url に対するアクションを選択**します。この設定が **オンに**なっていることを確認します。 <br/> &ensp;&ensp;* **疑わしいリンクおよびファイルを指すリンクのリアルタイム URL スキャンを適用**します。このチェックボックスをオンにします。 <br/> &ensp;&ensp;&ensp;&ensp;* **メッセージを配信する前に、URL のスキャンが完了するまで待機**します。このチェックボックスをオンにします。 <br/> &ensp;&ensp;* **[組織内で送信された電子メールメッセージに安全なリンクを適用する**]: このチェックボックスをオンにします。 <br/> &ensp;&ensp;* **ユーザーが元の URL に移動できないようにし**ます。このチェックボックスをオンにします。 <br/> &ensp;&ensp;* **適用先**: **受信者ドメインは、** \> ドメインを選択します。 <br/><br/> 詳細については、「 [安全なリンクポリシーを](set-up-atp-safe-links-policies.md)セットアップする」を参照してください。|
|**スパム対策 (メールフィルター)**|はい| 監視対象: <br/> &ensp;&ensp;* スパムが多すぎます-カスタム設定を選択し、既定のスパムフィルターポリシーを編集します。 <br/> &ensp;&ensp;* スプーフィングインテリジェンス—ドメインをスプーフィングしている送信者を確認します。 これらの送信者を禁止または許可します。 <br/><br/>詳細については [、「Microsoft 365 電子メールのスパム対策保護](anti-spam-protection.md)」を参照してください。|
|***電子メール認証***|はい|電子メール認証は、ドメインネームシステム (DNS) を使用して、電子メールの送信者に関する検証可能な情報を電子メールメッセージに追加します。 Microsoft 365 では、既定のドメイン (onmicrosoft.com) に対して電子メール認証を設定していますが、Microsoft 365 管理者はカスタムドメインに対して電子メール認証を使用することもできます。 3つの認証方法が使用されます。 <br/><br/> &ensp;&ensp;* Sender Policy Framework (または SPF)。<br/>&ensp;&ensp;&ensp;&ensp;-セットアップの場合は、「 [Microsoft 365 での SPF の設定」を](set-up-spf-in-office-365-to-help-prevent-spoofing.md)参照して、スプーフィングを防止してください。 <br/> &ensp;&ensp;* DomainKeys で識別されたメール (DKIM)。 <br/> &ensp;&ensp;&ensp;&ensp;-「 [DKIM を使用して、カスタムドメインから送信される送信電子メールを検証する」を](use-dkim-to-validate-outbound-email.md)参照してください。 <br/>&ensp;&ensp;&ensp;&ensp;-DKIM を構成した後、セキュリティセンターでそれを有効にします。<br/> &ensp;&ensp;* ドメインベースのメッセージ認証、レポート、および準拠 (DMARC)。 <br/> &ensp;&ensp;&ensp;&ensp;-DMARC セットアップの場合は、 [DMARC を使用して Microsoft 365 で電子メールを検証](use-dmarc-to-validate-email.md)します。|
|

> [!NOTE]
> SPF、ハイブリッド展開、およびトラブルシューティングの標準的でない展開の場合: [Microsoft 365 では、スプーフィングを防止するために Sender Policy Framework (SPF) を使用する方法](how-office-365-uses-spf-to-prevent-spoofing.md)について説明します。

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>セキュリティセンターとコンプライアンスセンターのダッシュボードとレポートを表示する

環境の正常性の詳細については、以下のレポートとダッシュボードを参照してください。 これらのレポートのデータは、組織が Office 365 サービスを使用しているほど充実したものになります。 ここでは、監視してアクションを実行できるものについて理解しておきます。 詳細については、「 [Microsoft 365 セキュリティセンターとコンプライアンスセンターのレポート](../../compliance/reports-in-security-and-compliance.md)」を参照してください。

****

|ダッシュボード|説明|
|---|---|
|[脅威管理ダッシュボード](security-dashboard.md)|セキュリティセンターの [ **脅威の管理** ] セクションで、このダッシュボードを使用して、既に処理されている脅威を確認し、ビジネス上の意思決定者に対して、ビジネスをセキュリティで保護するために既に行った脅威の調査と応答能力に関する便利なツールとして使用します。|
|[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)|これは、セキュリティセンターの [ **脅威の管理** ] セクションにもあります。 テナントに対する攻撃を調査中または経験している場合は、エクスプローラー (またはリアルタイムの検出) を使用して脅威を分析します。 エクスプローラー (およびリアルタイムの検出レポート) には、時間の経過と共に攻撃の量が表示されます。このデータは、脅威ファミリ、攻撃者のインフラストラクチャなどで分析できます。 インシデントリストに対して疑わしい電子メールをマークすることもできます。|
|レポート—ダッシュボード|セキュリティセンターの [ **レポート** ] セクションで、SharePoint Online および Exchange online 組織の監査レポートを表示します。 [ **レポートの表示** ] ページから、Azure Active Directory (azure ad) ユーザーのサインインレポート、ユーザーアクティビティレポート、および azure AD 監査ログにアクセスすることもできます。|
|

![セキュリティセンターダッシュボード](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>その他の Exchange Online テナント全体の設定を構成する

セキュリティセンターと Exchange 管理センターでのセキュリティと保護に関する多くのコントロールも、セキュリティセンターに含まれています。 両方の場所にこれらを構成する必要はありません。 推奨されるその他のいくつかの設定を以下に示します。

****

|分野|既定のポリシーが含まれています|推奨事項|
|---|---|---|
|**メールフロー** (メールフロールール (トランスポートルールとも呼ばれる)|いいえ|メールフロールールを追加して、ランサムウェアからの保護を促進します。マクロを含む実行可能ファイルの種類と Office ファイルの種類をブロックします。 詳細については、「 [メールフロールールを使用して Exchange Online のメッセージの添付ファイルを検査する](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)」を参照してください。 <br/><br/> その他のトピックを参照してください。 <br/>* [ランサムウェアから保護する](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)<br/>* [Office 365 でのマルウェアとランサムウェアの保護](https://docs.microsoft.com/Office365/Enterprise/office-365-malware-and-ransomware-protection) <br/>* [Office 365 でランサムウェア攻撃から回復する](recover-from-ransomware.md) <br/><br/> メールフロールールを作成して、外部ドメインに電子メールを自動的に転送できないようにします。 詳細については、「 [セキュリティで保護されたスコアでクライアントの外部転送ルールを軽減](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)する」を参照してください。 <br/><br/> 詳細情報: [Exchange Online のメールフロールール (トランスポートルール)](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**モダン認証を有効にする**|いいえ|モダン認証は、多要素認証 (MFA) を使用するための前提条件です。 メールを含むクラウドリソースへのアクセスを保護するために、MFA が推奨されています。 <br/><br/> 次のトピックを参照してください。 <br/>* [Exchange Online で先進認証を有効または無効にする](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) <br/>* [Skype for Business Online: 最新認証のためにテナントを有効にする](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/><br/> モダン認証は、Office 2016 クライアント、SharePoint Online、および OneDrive for business では既定で有効になっています。 <br/><br/> 詳細情報: [office 2013 および office 2016 クライアントアプリでの先進認証のしくみ](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>SharePoint 管理センターでテナント全体の共有ポリシーを構成する

SharePoint チームサイトを保護レベルを高くして構成する場合は、ベースライン保護から始めることをお勧めします。 詳細については、「 [Secure SharePoint Online sites and files](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files) 」を参照してください。

ベースラインレベルで構成された SharePoint チームサイトでは、匿名アクセスリンクを使用して外部ユーザーとファイルを共有できます。 この方法は、電子メールでファイルを送信する代わりに推奨されます。

ベースライン保護の目的をサポートするには、ここで推奨されているように、テナント全体の共有ポリシーを構成します。 個々のサイトの共有設定は、このテナント全体のポリシーよりも制限がありますが、制限はありません。

****

|分野|既定のポリシーが含まれています|推奨事項|
|---|---|---|
|**共有** (SharePoint Online と OneDrive for business)|はい|既定では、外部共有が有効になっています。 これらの設定をお勧めします。 <br/>* 認証済み外部ユーザーへの共有と匿名アクセスリンクの使用を許可します (既定の設定)。 <br/> * 匿名アクセスリンクの有効期限がこの日数を過ぎています。 必要に応じて、30日などの数値を入力します。 <br/>* 既定のリンクの種類— [内部] (組織内のユーザーのみ) を選択します。 匿名リンクを使用して共有を希望するユーザーは、[共有] メニューからこのオプションを選択する必要があります。 <br/><br/> 詳細情報: [外部共有の概要](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

SharePoint 管理センターと OneDrive for Business 管理センターには、同じ設定が含まれています。 どちらの管理センターの設定も、両方に適用されます。

## <a name="configure-settings-in-azure-active-directory"></a>Azure Active Directory で設定を構成する

セキュリティで保護された環境でのテナント全体のセットアップを完了するには、Azure Active Directory のこれら2つの領域を参照してください。

### <a name="configure-named-locations-under-conditional-access"></a>名前付きの場所を構成する (条件付きアクセスの場合)

セキュリティで保護されたネットワークアクセスを備えたオフィスが組織に含まれている場合は、名前付きの場所として、信頼できる IP アドレス範囲を Azure Active Directory に追加します。 この機能により、サインインリスクイベントに対して報告される誤検知の数を減らすことができます。

参照: [Azure Active Directory の名前付きの場所](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>モダン認証をサポートしていないアプリをブロックする

多要素認証では、先進認証をサポートするアプリが必要です。 モダン認証をサポートしていないアプリは、条件付きアクセスルールを使用してブロックすることはできません。

セキュリティで保護された環境では、先進認証をサポートしていないアプリの認証を無効にしてください。 Azure Active Directory でこれを行うには、近日中にコントロールを使用します。

その間、次のいずれかの方法を使用して、SharePoint Online と OneDrive for Business でこれを実行します。

- PowerShell を使用するには、「 [モダン認証 (ADAL) を使用していないアプリをブロックする](https://docs.microsoft.com/mem/intune/protect/app-modern-authentication-block)」を参照してください。

- これを SharePoint 管理センターの [デバイスアクセス] ページ ("モダン認証を使用していないアプリからアクセスを制御する") で構成します。 [ブロック] を選択します。

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Cloud App Security または Office 365 Cloud App Security の使用を開始する

Office 365 Cloud App Security を使用して、リスクを評価し、疑わしいアクティビティについての警告を行い、自動的にアクションを実行します。 Office 365 E5 プランが必要です。

または、Microsoft Cloud App Security を使用して、アクセスが許可された後でも、Office 365 を含むすべてのクラウドアプリケーションに対する包括的な制御と、保護を強化した後でも、より深い可視性を得ることができます。

このソリューションでは EMS E5 プランが推奨されるため、これを環境内の他の SaaS アプリケーションで使用できるように、Cloud App Security から始めることをお勧めします。 既定のポリシーと設定を使用して開始します。

詳しくは、以下の資料を参照してください。

- [Cloud App Security を展開する](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Microsoft Cloud App Security の詳細情報](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Cloud App Security とは](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security ダッシュボード](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>その他のリソース

これらの記事およびガイドは、Microsoft 365 環境をセキュリティ保護するための追加の規範的な情報を提供します。

- [政治的なキャンペーン、非営利組織、およびその他のアジャイル組織のための Microsoft security ガイダンス](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o) (特にクラウドのみの環境では、これらの推奨事項を使用できます)

- [Id とデバイスに推奨されるセキュリティポリシーと構成](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations) (これらの推奨事項は、AD FS 環境のヘルプを参照してください)
