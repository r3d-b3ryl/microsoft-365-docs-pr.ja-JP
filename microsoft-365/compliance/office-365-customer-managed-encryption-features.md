---
title: お客様が管理する暗号化機能
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: この記事では、Microsoft 365 で管理および構成できる暗号化テクノロジについて説明します。
ms.openlocfilehash: 3c7050ba0417473b4b387937336aae02c1eba778
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033615"
---
# <a name="customer-managed-encryption-features"></a>お客様が管理する暗号化機能

Microsoft によって管理される Microsoft 365 の暗号化テクノロジとともに、Microsoft 365 は、次のような管理および構成が可能な追加の暗号化テクノロジにも対応しています。

- [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [セキュリティで保護されたマルチパーパスインターネットメール内線番号](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Office 365 Message Encryption](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [パートナー組織とのセキュリティで保護されたメールフロー](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

これらのテクノロジの詳細については、 [Microsoft 365 サービスの説明](https://technet.microsoft.com/library/office-365-service-descriptions.aspx)を参照してください。

## <a name="azure-rights-management"></a>Azure Rights Management

Azure [Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) (azure RMS) は、 [azure Information protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)で使用される保護テクノロジです。 暗号化、id、および承認のポリシーを使用して、複数のプラットフォームとデバイス (電話、タブレット、Pc) 間でファイルと電子メールをセキュリティで保護することができます。 保護はデータと共に保持されるため、組織の内部と外部の両方で情報を保護することができます。 Azure RMS は、すべてのファイルの種類の永続的な保護を提供し、どこからでもファイルを保護し、ビジネス間のコラボレーション、および幅広い Windows デバイスと Windows 以外のデバイスをサポートします。 Azure RMS 保護は、[データ損失防止 (DLP) ポリシー](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)を強化することもできます。 Azure Information Protection から Azure Rights Management サービスを使用できるアプリケーションとサービスの詳細については、「[アプリケーションが Azure Rights management サービスをサポートする方法](https://docs.microsoft.com/information-protection/understand-explore/applications-support)」を参照してください。

Azure RMS は Microsoft 365 と統合されており、すべてのお客様が利用できます。 Azure RMS を使用するように Microsoft 365 を構成するには、「 [SharePoint 管理センターでの Azure Rights management を使用して Information Rights management (IRM) を設定するための IRM の構成](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx)」を参照してください。 オンプレミスの Active Directory (AD) RMS サーバーを運用している場合は、[オンプレミスの AD rms サーバーを使用する](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)ように IRM を構成することもできますが、他の組織とのセキュリティで保護されたコラボレーションなどの新しい機能を使用するには、 [Azure RMS に移行](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)することを強くお勧めします。

Azure RMS を使用して顧客データを保護する場合、Azure RMS は整合性を確保するために、2048ビットの RSA 非対称キーと SHA-256 ハッシュアルゴリズムを使用してデータを暗号化します。 Office ドキュメントおよび電子メールの対称キーは、AES 128 ビット (CBC モードの PKCS # 7 padding) です。 Azure RMS によって保護されているドキュメントまたは電子メールごとに、1つの AES キー ("コンテンツキー") が作成され、そのキーはドキュメントに埋め込まれており、ドキュメントの各エディションで保持されます。 コンテンツキーは、組織の RSA キー ("Azure Information Protection テナントキー") によってドキュメント内のポリシーの一部として保護され、そのポリシーはドキュメントの作成者によっても署名されます。 このテナントキーは、組織で Azure RMS によって保護されているすべてのドキュメントと電子メールに共通であり、このキーは、組織が顧客管理のテナントキーを使用している場合にのみ、Azure Information Protection 管理者が変更できます。 Azure RMS で使用される暗号化コントロールの詳細については、「Azure RMS のしくみ」を参照してください[。[内部] に](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)あります。

既定の Azure RMS 実装では、Microsoft はテナントごとに一意のルートキーを生成して管理します。 お客様は、Microsoft の FIPS 140-2 レベル2で検証された Hsm に移行した後に、オンプレミスの Hsm (ハードウェアセキュリティモジュール) でキーを生成できるようにするキー管理方法[(BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)を使用することにより、Azure Key Vault サービスを使用して azure RMS のルートキーのライフサイクルを管理できます。 キーをエクスポートしたり、Hsm から展開したりすることはできませんが、ユーザーにはルートキーへのアクセス権は付与されません。 さらに、ほぼリアルタイムログには、いつでもルートキーへのすべてのアクセス権が表示されます。 詳細については、「 [Azure Rights Management の使用状況のログと分析](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)」を参照してください。

Azure Rights Management を使用すると、ワイヤタップ、man-in-the-middle 攻撃、データ窃盗、組織の共有ポリシーの意図しない違反などの脅威を軽減できます。 同時に、適切なアクセス許可を持たない、承認されていないユーザーによる、送信中または保存中の顧客データの unwarranted アクセスは、そのデータを使用するポリシーによって禁止されているため、knowingly または気付かずに、データ損失防止機能が提供されます。 Azure Information Protection の一部として使用されている場合、Azure RMS はデータ分類とラベル付け機能、コンテンツマーキング、ドキュメントアクセス追跡、およびアクセス取り消し機能も提供します。 これらの機能の詳細に[ついては](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)、「azure information protection」、「 [azure information protection 展開ロードマップ](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)」、および「 [Quick Start チュートリアル for azure information protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)」を参照してください。

## <a name="secure-multipurpose-internet-mail-extension"></a>セキュリティで保護されたマルチパーパスインターネットメール内線番号

Secure/多目的インターネットメール内線 (S/MIME) は、公開キー暗号化と MIME データのデジタル署名の標準です。 S/MIME は、Rfc 3369、3370、3850、3851、その他で定義されています。 これにより、ユーザーは電子メールを暗号化し、電子メールにデジタル署名することができます。 S/MIME を使用して暗号化された電子メールは、秘密キーを使用して電子メールの受信者によってのみ復号化できます。これは、その受信者のみが利用できます。 そのため、電子メールの受信者以外は誰でも電子メールを復号化できません。

[Microsoft は S/MIME をサポート](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)しています。 パブリック証明書は、ユーザーのオンプレミスの Active Directory に配布され、Microsoft 365 テナントにレプリケートできる属性に保存されます。 公開キーに対応する秘密キーはオンプレミスのままであり、Office 365 に送信されることはありません。 ユーザーは、Outlook、web 上の Outlook、および Exchange ActiveSync クライアントを使用して、組織内の2人のユーザー間で電子メールを作成、暗号化、暗号化解除、読み取り、およびデジタル署名することができます。 詳細については、「 [Office 365 での S/MIME 暗号化の現在](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)の状態」を参照してください。

## <a name="office-365-message-encryption"></a>Office 365 Message Encryption

[Office 365 Message Encryption](https://products.office.com/exchange/office-365-message-encryption) (OME) は、 [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) (AIP) の上に構築されており、暗号化され、権利で保護されたメールをだれにでも送信できます。 OME は、ワイヤタップや man-in-the-middle 攻撃などの脅威、および適切なアクセス許可を持たない、承認されていないユーザーによるデータの unwarranted アクセスなどの脅威を軽減します。 Azure Information Protection の上に構築された、よりシンプルで直感的な安全な電子メールの操作性を提供する投資が行われています。 Microsoft 365 から組織の内部または外部のすべてのユーザーに送信されるメッセージを保護することができます。 これらのメッセージは、Azure Active Directory、Microsoft アカウント、Google Id などの任意の id を使用して、さまざまなメールクライアントのセットで表示できます。 組織が暗号化されたメッセージを使用する方法の詳細については、「 [Office 365 Message Encryption](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A)」を参照してください。

## <a name="transport-layer-security"></a>トランスポート層セキュリティ   

パートナーとの通信をセキュリティで保護する場合は、受信コネクタと送信コネクタを使用してセキュリティとメッセージの整合性を確保できます。 証明書を使用して、各コネクタで強制受信および送信 TLS を構成できます。 暗号化された SMTP チャネルを使用すると、man-in-the-middle 攻撃によってデータが盗まれるのを防ぐことができます。 詳細については、「 [Exchange Online が TLS を使用して電子メール接続をセキュリティで保護する方法](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F)」を参照してください。

## <a name="domain-keys-identified-mail"></a>ドメインキーによって識別されたメール

Exchange Online Protection (EOP) および Exchange Online では、ドメインキー識別メール (DKIM) メッセージの受信検証をサポートしています。 DKIM は、メッセージがドメインから送信されたことを検証する方法です。これは、そのメッセージが送信者からのものであり、他のユーザーによってスプーフィングされていないことを示します。 電子メールメッセージを送信しようとしている組織に関連付け、電子メールの暗号化に関して大きなパラダイムの一部となります。 このパラダイムの3つの部分の詳細については、以下を参照してください。

- [SPF を設定して、スプーフィングを防止する](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [DMARC を使用してメールを検証する](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
