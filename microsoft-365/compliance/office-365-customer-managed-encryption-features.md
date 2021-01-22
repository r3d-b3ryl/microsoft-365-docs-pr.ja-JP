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
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: この記事では、Microsoft 365 で管理および構成できる暗号化テクノロジについて説明します。
ms.openlocfilehash: bb6f9fedf915fd261266a9ed5d0c561d1352ea09
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921557"
---
# <a name="customer-managed-encryption-features"></a>顧客により管理される暗号化機能

Microsoft によって管理される Microsoft 365 の暗号化テクノロジに加え、Microsoft 365 は、次のような管理および構成が可能な追加の暗号化テクノロジと共に動作します。

- [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [Secure Multipurpose Internet Mail Extension](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Office 365 Message Encryption](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [パートナー組織とのセキュリティで保護されたメール フロー](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

これらのテクノロジの詳細については [、Microsoft 365 サービスの説明を参照してください](https://technet.microsoft.com/library/office-365-service-descriptions.aspx)。

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) (Azure RMS) は [、Azure Information Protection で使用される保護テクノロジです](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)。 暗号化、ID、および承認ポリシーを使用して、電話、タブレット、PC など、複数のプラットフォームとデバイス間でファイルと電子メールを保護します。 データに保護が残るために、組織内外の両方で情報を保護できます。 Azure RMS は、すべてのファイルの種類を永続的に保護し、ファイルを任意の場所で保護し、企業間のコラボレーション、およびさまざまな Windows デバイスと Windows 以外のデバイスをサポートします。 Azure RMS 保護は、データ損失 [防止 (DLP) ポリシーを拡張することもできます](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。 Azure Information Protection から Azure Rights Management サービスを使用できるアプリケーションとサービスの詳細については、「アプリケーションが Azure Rights Management サービスをサポートする方法」を [参照してください](https://docs.microsoft.com/information-protection/understand-explore/applications-support)。

Azure RMS は Microsoft 365 と統合され、すべてのお客様が利用できます。 Azure RMS を使用するように Microsoft 365 を構成するには、「Azure Rights Management を使用するように IRM を構成する」および「SharePoint 管理センターで [Information Rights Management (IRM)](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx)をセットアップする」を参照してください。 オンプレミスの Active Directory (AD) RMS サーバーを運用している場合は、オンプレミスの AD RMS サーバーを使用するように [IRM](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)を構成することもできますが [、Azure RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) に移行して、他の組織との安全な共同作業などの新機能を使用することを強く推奨します。

Azure RMS を使用して顧客データを保護する場合、Azure RMS は、データを暗号化するための整合性のために、SHA-256 ハッシュ アルゴリズムを持つ 2048 ビット RSA 非対称キーを使用します。 ドキュメントとメールOffice対称キーは AES 128 ビットです。 Azure RMS によって保護されているドキュメントまたは電子メールごとに、Azure RMS は 1 つの AES キー ("コンテンツ キー") を作成し、そのキーはドキュメントに埋め込み、ドキュメントのエディションを通じて保持されます。 コンテンツ キーは、ドキュメント内のポリシーの一部として組織の RSA キー ("Azure Information Protection テナント キー") で保護され、ポリシーはドキュメントの作成者によって署名されます。 このテナント キーは、組織の Azure RMS で保護されているすべてのドキュメントと電子メールに共通であり、このキーは、組織が顧客管理のテナント キーを使用している場合にのみ、Azure Information Protection 管理者が変更できます。 Azure RMS で使用される暗号化コントロールの詳細については、「Azure RMS の動作方法」 [を参照してください。Under the hood](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work).

既定の Azure RMS 実装では、Microsoft はテナントごとに一意のルート キーを生成して管理します。 顧客は、Azure Key Vault Services を使用して Azure RMS のルート キーのライフサイクルを管理できます。この管理方法は Bring [Your Own Key (BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key) と呼ばれるキー管理方法を使用することで、オンプレミスの HSM (ハードウェア セキュリティ モジュール) でキーを生成し、Microsoft の FIPS 140-2 レベル 2 検証済み HSM への転送後もこのキーを制御し続けることができます。 ルート キーへのアクセスは、キーを保護する HSM からエクスポートまたは抽出できないので、どの担当者にも与えされません。 さらに、ルート キーへのすべてのアクセスを示すほぼリアルタイムのログにいつでもアクセスできます。 詳細については [、「Azure Rights Management の使用状況のログ記録と分析」を参照してください](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)。

Azure Rights Management は、ワイヤータップ、man-in-the-middle 攻撃、データ盗難、組織共有ポリシーの意図しない違反などの脅威を軽減するのに役立ちます。 同時に、適切なアクセス許可を持たなかった未承認のユーザーによる、転送中または保存中の顧客データへの不正なアクセスは、そのデータに従うポリシーによって防止され、そのデータが知らないうちに不正な手に落ち、データ損失防止機能を提供するリスクを軽減します。 Azure Information Protection の一部として使用される場合、Azure RMS はデータ分類とラベル付け機能、コンテンツ マーキング、ドキュメント アクセス追跡、アクセス失効機能も提供します。 これらの機能の詳細については [、「Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)とは」、Azure Information Protection 展開ロードマップ、および Azure [Information](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)Protection のクイック スタート [チュートリアルを参照してください](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)。

## <a name="secure-multipurpose-internet-mail-extension"></a>Secure Multipurpose Internet Mail Extension

Secure/Multipurpose Internet Mail Extensions (S/MIME) は、公開キーの暗号化と MIME データのデジタル署名の標準です。 S/MIME は RFC 3369、3370、3850、3851 などで定義されています。 これにより、ユーザーは電子メールを暗号化し、電子メールにデジタル署名できます。 S/MIME を使用して暗号化された電子メールは、電子メールの受信者だけが秘密キーを使用して復号化できます。これは、その受信者だけが使用できます。 そのため、メールの受信者以外のユーザーがメールを復号化することはできません。

[Microsoft は S/MIME をサポートしています](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)。 パブリック証明書は、顧客のオンプレミスの Active Directory に配布され、Microsoft 365 テナントにレプリケートできる属性に格納されます。 公開キーに対応する公開キーはオンプレミスのままで、365 にOfficeされません。 ユーザーは、Outlook、Outlook on the web、および Exchange ActiveSync クライアントを使用して、組織内の 2 人のユーザー間で電子メールを作成、暗号化、暗号化解除、読み取り、デジタル署名できます。 詳細については [、365 で S/MIME 暗号化を参照Officeしてください](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)。

## <a name="office-365-message-encryption"></a>Office 365 Message Encryption

[Office 365 Message Encryption](https://products.office.com/exchange/office-365-message-encryption) (OME) を [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) (AIP) の上に構築すると、暗号化された権利で保護されたメールをすべてのユーザーに送信できます。 OME は、ワイヤータップや man-in-the-middle 攻撃などの脅威、および適切なアクセス許可を持たない承認されていないユーザーによるデータの不正なアクセスなど、その他の脅威を軽減します。 Azure Information Protection を基に構築された、よりシンプルで直感的で安全な電子メール エクスペリエンスを提供する投資を行いました。 Microsoft 365 から組織内外のユーザーに送信されるメッセージを保護できます。 これらのメッセージは、Azure Active Directory、Microsoft アカウント、Google ID など、任意の ID を使用して、さまざまなメール クライアントで表示できます。 組織で暗号化されたメッセージを使用する方法の詳細については、「Office [365 Message Encryption」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/ome)。

## <a name="transport-layer-security"></a>トランスポート層セキュリティ   

パートナーとの安全な通信を確保する場合は、受信コネクタと送信コネクタを使用して、セキュリティとメッセージの整合性を提供できます。 証明書を使用して、各コネクタで強制的な受信および送信 TLS を構成できます。 暗号化された SMTP チャネルを使用すると、man-in-the-middle 攻撃によってデータが盗まれるのを防ぐ可能性があります。 詳細については、「Exchange Online が [TLS を使用して電子メール接続をセキュリティで保護する方法」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)。

## <a name="domain-keys-identified-mail"></a>ドメイン キー識別メール

Exchange Online Protection (EOP) と Exchange Online は、ドメイン キー識別メール (DKIM) メッセージの受信検証をサポートします。 DKIM は、メッセージの送信元がドメインから送信され、他のユーザーによってスプーフィングされていないというメッセージを検証するためのメソッドです。 電子メール メッセージを送信する組織に結び付け、電子メールの暗号化というより大きなパラダイムの一部です。 このパラダイムの 3 つの部分の詳細については、以下を参照してください。

- [SPF を設定して、スプーフィングを防止する](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [DMARC を使用してメールを検証する](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
