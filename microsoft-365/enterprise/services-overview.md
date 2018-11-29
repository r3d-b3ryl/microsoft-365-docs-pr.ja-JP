---
title: Microsoft 365 Enterprise サービスの概要 | Microsoft Docs
description: この文書では、Microsoft 365 Enterprise と企業使用推奨事項の概要を提供します。
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 7772421a32abd863f4301a4bc3d8264d8fe44242
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869560"
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Microsoft 365 Enterprise のサービスと概念

Microsoft 365 Enterprise は大規模組織向けに設計されており、Office 365 Enterprise、Windows 10 Enterprise、および Enterprise Mobility + Security (EMS) と統合され、誰もが安全な環境で創造性を発揮しながらチームワークを高めることができます。 Microsoft 365 Enterprise には、Office 365 ProPlus を通して Windows 10 および Office アプリケーションの Enterprise Edition が組み込まれています。

Windows 10 と Office 365 ProPlus はどちらも、3 月と 9 月に半期チャネルで新機能リリースを提供します。 半期チャネルの機能のリリースは 18 か月間サポートされます。 Microsoft Intune と System Center Configuration Manager はどちらも、Windows 10 と Office 365 ProPlus をデプロイおよび更新するための機能を提供します。

Windows 10、Office 365 ProPlus、Microsoft Intune、および System Center Configuration Manager の最新バージョンを次に示します。

|     |**半期チャネル (対象)**|**半期チャネル**|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update (近日公開予定)|バージョン 1703|
|**Office 365 ProPlus**|バージョン 1803|バージョン 1708|
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

## <a name="important-concepts-to-understand"></a>理解するべき重要な概念
理解しておくべき中心的概念と EMS の各種機能を下の表にまとめています。

|中心的概念|説明|
|------------|-----------|
|[Azure 多要素認証 (MFA)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Microsoft の 2 段階認証ソリューションである Azure MFA を利用すると、ユーザーが求める簡単なサインイン プロセスを与え、同時にデータやアプリケーションへのアクセスを保護できます。 電話、テキスト メッセージ、モバイル アプリ検証など、さまざまな検証方法を利用し、強固な認証を実現します。|
|[Azure AD 条件付きアクセス](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Azure AD のこの機能を利用すると、環境内のクラウド アプリへのアクセスを特定の条件に基づいて制御できます。 制御では、アクセスに要件を追加するか、アクセスを禁止できます。 条件付きアクセスの実装は、ポリシーに基づきます。|
|[Exchange Online データ損失防止 (DLP)](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|Exchange Online データ損失防止 (DLP) ポリシーは Exchange Online Plan 2 と Office 365 サブスクリプションのプレミアム機能として利用できます。このポリシーを利用すると、組織は Office 365 全体の機密情報を特定し、監視し、自動的に保護できます。<br><br>Exchange Online DLP ポリシーでは、Exchange Online、SharePoint Online、OneDrive for Business など、さまざまな場所を対象に機密情報を特定できます。 たとえば、機密情報が含まれる文書を特定したり、組織の外部の人間と機密情報を間違って共有するような事態を回避したりできます。|
|[Exchange メール フロー/トランスポート ルール](https://support.office.com/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|Exchange のメール フロー ルールはトランスポート ルールとも呼ばれていますが、組織を通過するメッセージで特定の条件を探し、それに対処します。 メール フロー ルールは、多くのメール クライアントで利用できる受信トレイ ルールに似ています。 メール フロー ルールと Ouslook のようなクライアント アプリケーションで設定するルールの主な違いは、メール フロー ルールは、メッセージが届けられた後ではなく、転送中に適用されるということです。 また、メール フロー ルールには、条件、例外、アクションがたくさんあり、さまざまな種類のメッセージ ポリシーを柔軟に実装できます。|
|[Intune モバイル デバイス管理](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune は、モバイル オペレーティング システムで利用できるプロトコルまたは API を利用し、モバイル デバイス管理 (MDM) を提供します。 たとえば、デバイスを管理登録し、企業のサービスにアクセスするデバイスの目録を IT 部署に与えたり、会社のセキュリティ/正常性基準を満たすようにデバイスを構成したり、企業のサービスにアクセスするための証明書や Wi-Fi/VPN プロファイルを提供したり、企業の基準にデバイスが準拠しているか測定し、報告したり、管理対象デバイスから企業データを削除したりできます。|
|[Intune アプリ保護ポリシー](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|Intune アプリの保護ポリシーは、モバイル アプリ内の会社のデータを保護するために利用できます。デバイスは管理登録してもしなくてもかまいません。 実際、ユーザーのモバイル デバイスは Microsoft 以外の別の MDM ソリューションで管理できます。一方、[Office 365 の情報は Intune が保護します](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices)。 社員の生産性を落とさずに、意図的なデータ損失と意図しないデータ損失を防止できます。 アプリレベル ポリシーを実装することで、会社のリソースへのアクセスを制限し、データを IT 部門の管理範囲内に維持できます。|
|[Azure AD トークンの有効期間](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|Azure Active Directory (Azure AD) が発行するトークンの有効期間を指定できます。 組織のすべてのアプリ、マルチテナント (多組織) アプリケーション、組織の特定のサービス プリンシパルにトークンの有効期間を設定できます。|
|Microsoft Identity Brokers|Microsoft はあらゆるモバイル プラットフォームのために、さまざまなベンダー製のアプリケーションをまたいで資格情報を橋渡しし、資格情報の検証のために安全な場所を 1 つ要求する特別な拡張機能を可能にするアプリケーションを提供します。 これがブローカーと呼んでいる機能です。 iOS と Android では、Microsoft Authenticator アプリや Intune ポータル サイト アプリからブローカーが提供されます。 Windows 10 の場合、この機能はオペレーティング システムに組み込まれている、Web Authentication Broker と呼ばれているアカウント選択機能により提供されます。|

## <a name="security-best-practices-and-recommendations"></a>セキュリティ上のベスト プラクティスと推奨事項
すべての顧客環境に最適な推奨事項は 1 つだけではありませんが、「[推奨されるセキュリティ ポリシーと構成](microsoft-365-policies-configurations.md)」の記事では、重要なセキュリティのベスト プラクティスの概念について説明します。 この記事では、従業員のセキュリティの保護と生産性の両方を保証するために、Microsoft クラウド内でポリシーと構成を適用する方法について、一般的な Microsoft の推奨事項も説明します。

### <a name="baseline-recommended-security-policies-and-configurations"></a>基準として推奨されるセキュリティ ポリシーと構成
[一般的な ID とデバイス アクセス ポリシーの推奨事項](identity-access-policies.md)では、Microsoft 365 Enterprise をセキュリティで保護するために役立つ、一般的に推奨されるポリシーについて説明します。 既定のプラットフォーム クライアント構成に関する記載もありますが、ユーザーには最も使いやすい SSO と、条件付きアクセスのための技術的前提条件を提供することが推奨されます。

### <a name="exchange-online-access-policies"></a>Exchange Online アクセス ポリシー
[電子メールをセキュリティで保護するためのポリシー推奨事項](secure-email-recommended-policies.md)では、組織のメールの保護と先進認証と条件付きアクセスをサポートしているメール クライアントの保護に役立つ、Microsoft の推奨事項を示します。 これらの推奨事項は、[共通 ID とアクセス ポリシーの推奨事項](identity-access-policies.md)に加えられます。

### <a name="sharepoint-online-access-policies"></a>SharePoint Online アクセス ポリシー
推奨事項は、[共通 ID とアクセス ポリシーの推奨事項](identity-access-policies.md)および[電子メールをセキュリティで保護するためのポリシー推奨事項](secure-email-recommended-policies.md)に加えて、[SharePoint Online ファイル アクセスを保護する](sharepoint-file-access-policies.md)ために示されます。 この記事では、Exchange Online 電子メールと SharePoint Online ファイル アクセスの両方を保護するために、作成する必要がある新しいポリシー、および既存のポリシーをどのように修正するかについて説明します。

## <a name="deploy-windows-10-and-office-365-proplus"></a>Windows 10 および Office 365 ProPlus のデプロイ
Windows 10 および Office 365 ProPlus をデプロイし、Microsoft Azure Active Directory (Azure AD) またはオンプレミスの Active Directory Domain Services (AD DS) に統合する方法を説明します。 Windows 10、Office 365 ProPlus、およびその他の基幹業務アプリを新しいデバイスにデプロイするか、Intune、System Center Configuration Manager、およびデバイスを管理するグループ ポリシーを使用して既存のデバイスを Windows 10 にアップグレードします。

詳細については、次の各資料を参照してください。
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
