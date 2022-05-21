---
title: 顧客により管理される暗号化機能
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: この記事では、Microsoft 365で管理および構成できる暗号化テクノロジについて説明します。
ms.openlocfilehash: 55bc743f83b79ac83c764af24ef4100e5f72369d
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65622555"
---
# <a name="customer-managed-encryption-features"></a>顧客により管理される暗号化機能

- [Azure Rights Management](/azure/information-protection/what-is-azure-rms)

- [Microsoft Purview のメッセージの暗号化](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [パートナー組織とのメール フローをセキュリティで保護する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

これらのテクノロジの詳細については、[Microsoft 365サービスの説明](/office365/servicedescriptions/office-365-service-descriptions-technet-library)を参照してください。

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](/azure/information-protection/what-is-azure-rms) (Azure RMS) は、[Azure Information Protection](/information-protection/understand-explore/what-is-information-protection)で使用される保護テクノロジです。 暗号化、ID、承認ポリシーを使用して、複数のプラットフォームやデバイス (スマートフォン、タブレット、PC) でファイルと電子メールをセキュリティで保護します。 保護はデータに残るため、組織内外の両方で情報を保護できます。 Azure RMS は、あらゆる種類のファイルを永続的に保護し、あらゆる場所でファイルを保護し、企業間コラボレーションをサポートし、さまざまなWindowsデバイスと非Windows デバイスをサポートします。 Azure RMS 保護は、 [データ損失防止 (DLP) ポリシー](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)を強化することもできます。 Azure Information Protectionから Azure Rights Management サービスを使用できるアプリケーションとサービスの詳細については、「アプリケーションで Azure [Rights Management サービスをサポートする方法」を](/information-protection/understand-explore/applications-support)参照してください。

Azure RMS はMicrosoft 365と統合され、すべてのお客様が利用できます。 Azure RMS を使用するようにMicrosoft 365を構成するには、[管理センターで Azure Rights Managementを使用するように IRM を構成し、SharePoint情報Rights Management (IRM) を設定する方法に関するページを参照](../enterprise/activate-rms-in-microsoft-365.md)してください。 オンプレミスの Active Directory (AD) RMS サーバーを運用している場合は、[オンプレミスの AD RMS サーバーを使用するように IRM を構成](/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)することもできますが、[Azure RMS に移行](/azure/information-protection/migrate-from-ad-rms-to-azure-rms)して、他の組織とのセキュリティで保護されたコラボレーションなどの新機能を使用することを強くお勧めします。

Azure RMS を使用して顧客データを保護する場合、Azure RMS は 2048 ビット RSA 非対称キーと SHA-256 ハッシュ アルゴリズムを使用してデータを暗号化します。 Officeドキュメントと電子メールの対称キーは AES 128 ビットです。 Azure RMS によって保護されているドキュメントまたは電子メールごとに、Azure RMS によって 1 つの AES キー ("コンテンツ キー") が作成され、そのキーがドキュメントに埋め込まれ、ドキュメントのエディションを通じて保持されます。 コンテンツ キーは、ドキュメント内のポリシーの一部として組織の RSA キー ("Azure Information Protection テナント キー") で保護され、ポリシーもドキュメントの作成者によって署名されます。 このテナント キーは、組織の Azure RMS によって保護されているすべてのドキュメントと電子メールに共通であり、組織がカスタマー マネージドのテナント キーを使用している場合、このキーは Azure Information Protection管理者のみが変更できます。 Azure RMS で使用される暗号化制御の詳細については、「Azure RMS のしくみ」を参照してください [。内部の下](/information-protection/understand-explore/how-does-it-work)。

既定の Azure RMS 実装では、Microsoft はテナントごとに一意のルート キーを生成して管理します。 お客様は、オンプレミス HSM (ハードウェア セキュリティ モジュール) でキーを生成し、Microsoft の FIPS 140-2 レベル 2 検証済み HSM に転送した後も、このキーを制御し続けることができる Bring [Your Own Key (BYOK)](/azure/information-protection/plan-implement-tenant-key) というキー管理方法を使用して、Azure Key Vault Services を使用して Azure RMS でルート キーのライフサイクルを管理できます。 ルート キーへのアクセスは、キーを保護する HSM からエクスポートまたは抽出できないため、担当者には付与されません。 さらに、ルート キーへのすべてのアクセスを示すほぼリアルタイムのログにいつでもアクセスできます。 詳細については、「[Azure Rights Management使用状況のログ記録と分析」を参照してください](/azure/information-protection/log-analyze-usage)。

Azure Rights Managementは、ネットワーク タップ、中間者攻撃、データ盗難、組織共有ポリシーの意図しない違反などの脅威を軽減するのに役立ちます。 同時に、転送中または適切なアクセス許可を持たない承認されていないユーザーによる顧客データの不当なアクセスは、そのデータに従うポリシーによって防止され、そのデータが誤った手に落ちるリスクを軽減し、データ損失防止機能を提供します。 Azure Information Protectionの一部として使用される場合、Azure RMS では、データ分類とラベル付け機能、コンテンツ マーキング、ドキュメント アクセスの追跡、アクセス失効機能も提供されます。 これらの機能の詳細については、「[Azure Information Protectionとは」](/information-protection/understand-explore/what-is-information-protection)、[Azure Information Protectionデプロイ ロードマップ](/information-protection/plan-design/deployment-roadmap)、および [Azure Information Protectionのクイック スタートチュートリアル](/information-protection/get-started/infoprotect-quick-start-tutorial)を参照してください。

## <a name="secure-multipurpose-internet-mail-extension"></a>Secure Multipurpose Internet Mail Extension

Secure/Multipurpose Internet Mail Extensions (S/MIME) は、公開キーの暗号化と MIME データのデジタル署名の標準です。 S/MIME は RFC 3369、3370、3850、3851 などで定義されます。 これにより、ユーザーは電子メールを暗号化し、電子メールにデジタル署名できます。 S/MIME を使用して暗号化された電子メールは、秘密キーを使用して電子メールの受信者のみが復号化できます。これは、その受信者のみが使用できます。 そのため、電子メールの受信者以外のユーザーが電子メールを復号化することはできません。

[Microsoft では S/MIME がサポートされています](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)。 パブリック証明書は顧客のオンプレミスの Active Directoryに配布され、Microsoft 365 テナントにレプリケートできる属性に格納されます。 公開キーに対応する秘密キーはオンプレミスのままであり、Office 365には送信されません。 ユーザーは、Outlook、Outlook on the web、およびExchange ActiveSyncクライアントを使用して、組織内の 2 人のユーザー間で電子メールを作成、暗号化解除、復号化、読み取り、デジタル署名できます。 詳細については、[Office 365の S/MIME 暗号化に関するOffice 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)を参照してください。

## <a name="office-365-message-encryption"></a>Office 365 Message Encryption

[Azure](/information-protection/understand-explore/what-is-information-protection) Information Protection (AIP) 上に構築された [Office 365 メッセージ暗号化](https://products.office.com/exchange/office-365-message-encryption) (OME) を使用すると、暗号化された権限で保護されたメールをだれにでも送信できます。 OME は、ワイヤタップや中間者攻撃などの脅威や、適切なアクセス許可を持たない未承認のユーザーによるデータへの不当なアクセスなどの他の脅威を軽減します。 Azure Information Protectionの上に構築された、よりシンプルで直感的で安全な電子メール エクスペリエンスを提供する投資を行いました。 Microsoft 365から組織内外のユーザーに送信されたメッセージを保護できます。 これらのメッセージは、Azure Active Directory、Microsoft アカウント、Google ID など、任意の ID を使用して、さまざまなメール クライアントのセットで表示できます。 組織で暗号化されたメッセージを使用する方法の詳細については、「[Office 365 メッセージの暗号化](./ome.md)」を参照してください。

## <a name="transport-layer-security"></a>トランスポート層セキュリティ   

パートナーとの安全な通信を確保する場合は、受信コネクタと送信コネクタを使用して、セキュリティとメッセージの整合性を提供できます。 証明書を使用して、各コネクタで強制的に受信 TLS と送信 TLS を構成できます。 暗号化された SMTP チャネルを使用すると、中間者攻撃によってデータが盗まれるのを防ぐことができます。 詳細については、「[Exchange Onlineが TLS を使用して電子メール接続をセキュリティで保護する方法」を](./exchange-online-uses-tls-to-secure-email-connections.md)参照してください。

## <a name="domain-keys-identified-mail"></a>ドメイン キーが識別されたメール

Exchange Online Protection (EOP) とExchange Onlineは、ドメイン キー識別メール (DKIM) メッセージの受信検証をサポートします。 DKIM は、メッセージが送信元のドメインから送信されたこと、および他のユーザーによってスプーフィングされなかったことを検証するためのメソッドです。 電子メール メッセージを送信する組織に結び付け、電子メール暗号化のより大きなパラダイムの一部です。 このパラダイムの 3 つの部分の詳細については、次を参照してください。

- [SPF を設定して、スプーフィングを防止する](/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する](/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [DMARC を使用してメールを検証する](/office365/SecurityCompliance/use-dmarc-to-validate-email)
