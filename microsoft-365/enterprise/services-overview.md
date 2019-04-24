---
title: Microsoft 365 Enterprise services の概要 |Microsoft Docs
description: このコンテンツでは、Microsoft 365 enterprise および enterprise の使用に関する推奨事項の概要を説明します。
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 7772421a32abd863f4301a4bc3d8264d8fe44242
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290162"
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Microsoft 365 Enterprise のサービスと概念

Microsoft 365 Enterprise は大規模組織向けに設計されており、Office 365 Enterprise、Windows 10 Enterprise、および Enterprise Mobility + Security (EMS) と統合され、誰もが安全な環境で創造性を発揮しながらチームワークを高めることができます。 Microsoft 365 Enterprise には、Office 365 ProPlus を通して Windows 10 および Office アプリケーションの Enterprise Edition が組み込まれています。

Windows 10 と Office 365 ProPlus はどちらも、3 月と 9 月に半期チャネルで新機能リリースを提供します。 半期チャネルの機能のリリースは 18 か月間サポートされます。 Microsoft Intune と System Center Configuration Manager はどちらも、Windows 10 と Office 365 ProPlus をデプロイおよび更新するための機能を提供します。

Windows 10、Office 365 ProPlus、Microsoft Intune、および System Center Configuration Manager の最新バージョンを次に示します。

|     |**半期チャネル (対象指定)**|**半期チャネル**|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update (近日公開予定)|バージョン 1703|
|**Office 365 ProPlus**|バージョン1803|バージョン 1708|
|**Intune**|N/A|バージョン 1708|
|**System Center Configuration Manager**|Technical Preview バージョン 1708|バージョン 1706<sup>*</sup>|

<sup>*</sup> System Center Configuration Manager の現在のブランチの更新プログラム 1706 は、バージョン 1606、1610、1702 が実行されている以前にインストールされたサイト向けのコンソール内更新プログラムとして利用可能です。

> [!NOTE]
> Microsoft Azure サービスも定期的に更新されますが、バージョン番号では参照されません。 最新の更新プログラムや Azure サービスの最新情報を確認するには、[クラウド プラットフォームのロードマップ](https://www.microsoft.com/cloud-platform/roadmap)に関するページをご覧ください。

これらのバージョンで使用できる機能の詳細については、次の記事をご覧ください。
- [Windows 10 の新機能](https://docs.microsoft.com/windows/whats-new/)
- [Windows 10 のリリース情報](https://technet.microsoft.com/windows/release-info)
- [Windows 10 の更新履歴](https://support.microsoft.com/help/4018124/windows-10-update-history)
- [Office 365 クライアント更新プログラム チャネルのリリース](https://technet.microsoft.com/office/mt465751)
- [Microsoft Intune の新機能](https://docs.microsoft.com/intune/whats-new)
- [System Center Configuration Manager の新機能](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-incremental-versions)
- [System Center Configuration Manager の Technical Preview 1708 の機能](https://docs.microsoft.com/sccm/core/get-started/capabilities-in-technical-preview-1708)

## <a name="services-overview"></a>サービスの概要

このセクションでは、Microsoft 365 Enterprise に含まれる EMS と Office 365 サービスの概要を提供します。また、組織のニーズに合わせた最も効果的な利用方法を理解するために必要な中心的概念を紹介します。 サービスで提供される機能を利用すると、Microsoft クラウドの企業管理者は社員の ID やデバイスを守るだけでなく、送信中や保存されている会社のデータ自体に対するアクセスも制御できます。

|サービス|説明|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|Azure AD は、多要素認証、デバイス登録、セルフサービス パスワード管理、セルフサービス グループ管理、役割ベースのアクセス制御、アプリケーションの使用状況監視、機能が豊富な監査/セキュリティ監視、警告など、ID 管理機能の一式を提供します。|
|[Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|このサービスでは、組織の ID 保護を脅かす可能性がある脆弱性を検出し、条件付きアクセス ポリシーを利用して応答を自動化できます。アクセス ポリシーは、低、中、高のサインイン リスクまたはユーザー リスクに設定できます。|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|このサービスを利用すると、企業は特権が必要な操作に対する永続的アクセスを与える人の数を最小に抑えることができます。Azure AD Privileged Identity Management では、対象の管理者の概念を導入しています。対象の管理者とは、特権アクセスを毎日ではないが時折必要とするユーザーです。 ユーザーがアクセスを必要とするまで、この役割は非アクティブです。アクセスが必要になったらアクティブ化プロセスを完了し、事前に決定された時間だけアクティブな管理者になります。|
|[Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| Azure Information Protection は、組織が文書や電子メールを、分類、ラベル付けおよび保護するのに役立つクラウドベースのソリューションです。EMS E5 サービスの一部として提供されます。 これは、ルールや条件を定義する管理者が自動で実行するか、推奨が提示されたユーザーが手動で実行するか、両者で実行します。 Azure Information Protection のラベルは、文書と電子メールを分類するために使用します。 これを行うと、データの保存場所やデータの共有者に関係なく、いつでも分類を識別できるようになります。<br><br>Azure Information Protection ポリシー設定は [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms) で保護されています。 ラベルの適用方法と同様に、Rights Management で適用される保護は、場所、つまり、組織、ネットワーク、ファイル サーバー、アプリケーションの中にあるか外にあるかに関係なく、文書や電子メールに適用され続けます。|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune はクラウドベースのエンタープライズ モビリティ管理 (EMM) サービスであり、会社のデータを守りながら、社員に生産的に働いてもらうことができます。 Intune は Azure AD と緊密に連動して ID とアクセスを制御し、デバイスやアプリケーションの管理に利用されます。 [Intune のデバイス管理](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)機能は、Windows PC など、ユーザーのデバイスの構成と保護に利用されます。<br><br>Intune デバイス管理機能は [Bring Your Own Device (BYOD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod) 登録と [Corporate-owned Device (COD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices) 登録の両方に対応しています。BYOD は、ユーザーが個人のスマートフォン、タブレット、PC を登録できるしくみです。COD は、自動登録、共有デバイス、事前承認登録の要件構成などの管理シナリオを可能にします。 セキュリティ強化のために、デバイスの登録に MFA を要求することもできます。 管理に登録すると、会社のリソースに安全にアクセスできるように Intune でデバイスの機能と設定を構成できます。|

## <a name="important-concepts-to-understand"></a>理解しておくべき重要な概念
次の表に、理解しておく必要のある基本的な概念と EMS 機能を示します。

|中心概念|説明|
|------------|-----------|
|[Azure 多要素認証 (MFA)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Microsoft の2段階認証ソリューションとして、Azure MFA は、簡単なサインインプロセスに対するユーザーの要求を満たしながら、データやアプリケーションへのアクセスを保護するのに役に立ちます。 電話、テキストメッセージ、モバイルアプリの検証など、さまざまな検証方法を使用して強力な認証を提供します。|
|[Azure AD 条件付きアクセス](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Azure AD のこの機能により、特定の条件に基づいて環境内のクラウドアプリへのアクセスを制御することができます。 コントロールを使用すると、追加の要件をアクセスに割り当てることができます。または、それをブロックすることもできます。 条件付きアクセスの実装は、ポリシーに基づいています。|
|[Exchange Online データ損失防止 (DLP)](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|exchange online のデータ損失防止 (DLP) ポリシー。 exchange online プラン2および office 365 のサブスクリプションのプレミアム機能として利用でき、組織は office 365 全体の機密情報を特定、監視、および自動的に保護することができます。<br><br>exchange online の DLP ポリシーを使用すると、exchange online、SharePoint Online、OneDrive for business などのさまざまな場所で機密情報を識別できます。 たとえば、これらのポリシーは、機密情報が含まれているドキュメントを特定したり、機密情報が組織外のユーザーと誤って共有されたりするのを防ぐのに役立ちます。|
|[Exchange メールフロー/トランスポートルール](https://support.office.com/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|Exchange メールフロールール (トランスポートルールとも呼ばれます) は、組織を通過し、それらに対して実行されるメッセージ内の特定の条件を検索します。 メールフロールールは、多くの電子メールクライアントで利用できる受信トレイルールに似ています。 Outlook などのクライアントアプリケーションで設定するメールフロールールとルールの主な違いは、メールフロールールは、メッセージが配信された後ではなく、送信中のメッセージに対して動作するということです。 メールフロールールには、豊富な条件、例外、アクションが含まれており、さまざまな種類のメッセージングポリシーを柔軟に実装することができます。|
|[Intune モバイルデバイス管理](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune は、モバイルオペレーティングシステムで使用可能なプロトコルまたは api を使用して、モバイルデバイス管理 (MDM) を提供します。 これには、デバイスを管理に登録して、企業サービスにアクセスしているデバイスのインベントリを確保し、会社のセキュリティと正常性の標準を満たし、証明書と wi-fi/VPN プロファイルを提供するようにデバイスを構成するなどのタスクが含まれています。企業サービスへのアクセス、企業標準へのデバイスコンプライアンスの報告と測定、管理対象デバイスからの企業データの削除を行います。|
|[Intune アプリ保護ポリシー](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|Intune アプリ保護ポリシーを使用すると、モバイルアプリでデバイスを管理したり、登録したりすることなく、会社のデータを保護することができます。 実際、ユーザーのモバイルデバイスは、Microsoft 以外の別の MDM ソリューションで管理することができますが、 [Intune は Office 365 情報を保護](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices)するのに役に立ちます。 従業員が依然として生産性を維持できるようにする一方で、意図的かつ意図しないデータ損失を防ぐこともできます。 アプリレベルのポリシーを実装することで、会社のリソースへのアクセスを制限し、データを IT 部門のコントロール内に保持することができます。|
|[Azure AD トークンの有効期間](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|azure Active Directory (azure AD) によって発行されるトークンの有効期間を指定できます。 組織内のすべてのアプリ、マルチテナント (複数の組織) アプリケーション、または組織内の特定のサービスプリンシパルに対してトークンの有効期間を設定できます。|
|Microsoft id ブローカー|Microsoft では、さまざまなベンダーのアプリケーション間で資格情報をブリッジできるようにするすべてのモバイルプラットフォーム用のアプリケーションを提供しており、資格情報の検証に必要なセキュリティで保護された1つの場所を必要とする特別な拡張機能を使用できます。 これらのブローカーを呼び出します。 iOS および Android では、これらのブローカーは Microsoft Authenticator および Intune ポータルサイトアプリによって提供されます。 Windows 10 では、この機能は、オペレーティングシステム (技術的には Web 認証ブローカーとも呼ばれます) に組み込まれたアカウント選択によって提供されます。|

## <a name="security-best-practices-and-recommendations"></a>セキュリティ上のベスト プラクティスと推奨事項
すべての顧客環境に最適な推奨事項は 1 つだけではありませんが、「[推奨されるセキュリティ ポリシーと構成](microsoft-365-policies-configurations.md)」の記事では、重要なセキュリティのベスト プラクティスの概念について説明します。 この記事では、従業員のセキュリティの保護と生産性の両方を保証するために、Microsoft クラウド内でポリシーと構成を適用する方法について、一般的な Microsoft の推奨事項も説明します。

### <a name="baseline-recommended-security-policies-and-configurations"></a>ベースラインで推奨されるセキュリティポリシーと構成
[id およびデバイスアクセスポリシーに関する一般的な推奨事項](identity-access-policies.md)Microsoft 365 Enterprise をセキュリティで保護するための一般的な推奨ポリシーについて説明します。 既定のプラットフォーム クライアント構成に関する記載もありますが、ユーザーには最も使いやすい SSO と、条件付きアクセスのための技術的前提条件を提供することが推奨されます。

### <a name="exchange-online-access-policies"></a>Exchange Online アクセス ポリシー
[電子メールのセキュリティ保護に役立つポリシー推奨事項](secure-email-recommended-policies.md)組織の電子メールを保護するための Microsoft の推奨事項と、モダン認証および条件付きアクセスをサポートする電子メールクライアントについて説明します。 これらの推奨事項は、[共通 ID とアクセス ポリシーの推奨事項](identity-access-policies.md)に加えられます。

### <a name="sharepoint-online-access-policies"></a>SharePoint Online アクセス ポリシー
推奨事項は、[一般的な id およびアクセスポリシーの推奨](identity-access-policies.md)事項と、[電子メールのセキュリティ保護に役立つポリシーの推奨](secure-email-recommended-policies.md)事項に加えて、 [SharePoint Online ファイルアクセスを保護](sharepoint-file-access-policies.md)するために提供されています。 この記事では、Exchange online の電子メールと SharePoint online のファイルアクセスの両方を保護するために、作成する必要がある新しいポリシーと、既存のポリシーをどのように修正する必要があるかについて説明します。

## <a name="deploy-windows-10-and-office-365-proplus"></a>Windows 10 および Office 365 ProPlus のデプロイ
Windows 10 および Office 365 ProPlus をデプロイし、Microsoft Azure Active Directory (Azure AD) またはオンプレミスの Active Directory Domain Services (AD DS) に統合する方法を説明します。 Windows 10、Office 365 ProPlus、およびその他の基幹業務アプリを新しいデバイスにデプロイするか、Intune、System Center Configuration Manager、およびデバイスを管理するグループ ポリシーを使用して既存のデバイスを Windows 10 にアップグレードします。

詳細については、以下の記事を参照してください。
- [Windows 10 のデプロイに関する考慮事項](https://docs.microsoft.com/windows/deployment/planning/windows-10-deployment-considerations)
- [Office 365 ProPlus のデプロイ ガイド](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus)
- [企業に Office 365 ProPlus をデプロイするためのベスト プラクティス ガイド](https://docs.microsoft.com/DeployOffice/best-practices/best-practices)
- [Intune を使用して Windows 10 デバイスに Office 365 ProPlus アプリをデプロイする](https://docs.microsoft.com/intune/apps-add-office365)

Microsoft 365 のデプロイのサポートについては、[FastTrack にお問い合わせください](https://fasttrack.microsoft.com/microsoft365)。

## <a name="manage-updates-to-windows-10-and-office-365-proplus"></a>Windows 10 および Office 365 ProPlus への更新の管理
次のリンクで、Windows 10 および Office 365 ProPlus の品質と機能の更新を最大限に制御する方法を示します。 帯域幅の使用を効果的に制御し、最新機能とセキュリティ更新を使用して Windows および Office を最新に保つ方法について説明します。

詳細については、次の各資料を参照してください。
- [サービスとしての Windows の概要](https://docs.microsoft.com/windows/deployment/update/waas-overview)
- [Office 365 ProPlus 更新プログラム チャネルの概要](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)
- [Intune を使用したソフトウェア更新プログラムの管理](https://docs.microsoft.com/intune/windows-update-for-business-configure)
- [System Center Configuration Manager を使用した Windows 10 更新プログラムのデプロイ](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)<sup>*</sup>
- [Configuration Manager を使用した Office 365 ProPlus の管理](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

<sup>*</sup>Microsoft は、現在 Configuration Manager for Windows を使用している組織が、管理を更新して Windows 10 クライアント コンピューターでもこれを使用し続けることを推奨しています。

## <a name="next-steps"></a>次のステップ
[Microsoft 365 Enterprise 製品ページ](https://www.microsoft.com/microsoft-365/enterprise)<br/>
[クラウド プラットフォームのロードマップ](https://www.microsoft.com/cloud-platform/roadmap)
