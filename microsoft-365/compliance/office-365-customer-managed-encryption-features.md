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
description: この記事では、管理および構成できる暗号化テクノロジについて、Microsoft 365。
ms.openlocfilehash: 6a693c512100c59eef47414fdd6eab4a2924e835
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216713"
---
# <a name="customer-managed-encryption-features"></a>顧客により管理される暗号化機能

Microsoft が管理する Microsoft 365の暗号化テクノロジに加Microsoft 365、次のような管理および構成が可能な追加の暗号化テクノロジも使用できます。

- [Azure Rights Management](/azure/information-protection/what-is-azure-rms)

- [Secure Multipurpose Internet Mail Extension](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Office 365 Message Encryption](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [パートナー組織によるメール フローのセキュリティ保護](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

これらのテクノロジの詳細については、「サービスの説明[」Microsoft 365参照してください](/office365/servicedescriptions/office-365-service-descriptions-technet-library)。

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](/azure/information-protection/what-is-azure-rms) (Azure RMS) は、Azure Information Protection で使用される [保護テクノロジです](/information-protection/understand-explore/what-is-information-protection)。 暗号化、ID、および承認ポリシーを使用して、複数のプラットフォームとデバイス (電話、タブレット、PC) 間でファイルと電子メールをセキュリティで保護します。 データに保護が残るために、組織内外の両方で情報を保護できます。 Azure RMS は、すべてのファイルの種類を永続的に保護し、ファイルを任意の場所で保護し、企業間のコラボレーションをサポートし、Windows デバイスと非 Windows デバイスを幅広くサポートします。 Azure RMS 保護は、データ損失 [防止 (DLP) ポリシーを強化することもできます](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。 Azure Information Protection の Azure Rights Management サービスを使用できるアプリケーションとサービスの詳細については、「アプリケーションが Azure Rights Management サービスをサポートする方法」 [を参照してください](/information-protection/understand-explore/applications-support)。

Azure RMS は、すべてのユーザーがMicrosoft 365と統合され、利用できます。 Azure RMS をMicrosoft 365構成するには、「Azure Rights Management を使用するように IRM を構成する」および「管理センターで Information [Rights Management (IRM)](../enterprise/activate-rms-in-microsoft-365.md)を設定する」を参照SharePointしてください。 オンプレミスの Active Directory (AD) RMS サーバーを運用する場合は、オンプレミスの AD RMS サーバーを使用するように [IRM](/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)を構成することもできますが、Azure [RMS](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) に移行して、他の組織との安全なコラボレーションなどの新機能を使用することを強く推奨します。

Azure RMS を使用して顧客データを保護する場合、Azure RMS は、データを暗号化するための整合性のために SHA-256 ハッシュ アルゴリズムを使用して 2048 ビットの RSA 非対称キーを使用します。 ドキュメントと電子メールOffice対称キーは AES 128 ビットです。 Azure RMS によって保護されている各ドキュメントまたは電子メールについて、Azure RMS は単一の AES キー ("コンテンツ キー") を作成し、そのキーはドキュメントに埋め込み、ドキュメントのエディションを通じて保持されます。 コンテンツ キーは、ドキュメント内のポリシーの一部として組織の RSA キー ("Azure Information Protection テナント キー") で保護され、ポリシーはドキュメントの作成者によっても署名されます。 このテナント キーは、組織の Azure RMS によって保護されているすべてのドキュメントと電子メールに共通であり、このキーは、組織が顧客管理のテナント キーを使用している場合にのみ、Azure Information Protection 管理者によって変更できます。 Azure RMS で使用される暗号化コントロールの詳細については[、「Azure RMS の動作方法」を参照してください。ボンネットの下.](/information-protection/understand-explore/how-does-it-work)

既定の Azure RMS 実装では、Microsoft はテナントごとに一意のルート キーを生成および管理します。 Azure KEY Vault Services で Azure RMS のルート キーのライフサイクルを管理するには、オンプレミスの HSM (ハードウェア セキュリティ モジュール) でキーを生成し、Microsoft の FIPS 140-2 レベル 2 検証済み HSM への転送後もこのキーを制御できるキー管理メソッド Bring [Your Own Key (BYOK)](/azure/information-protection/plan-implement-tenant-key) を使用します。 ルート キーへのアクセスは、キーを保護する HSM からエクスポートまたは抽出できないので、どの担当者にも与えされません。 さらに、ルート キーへのすべてのアクセスを示すほぼリアルタイム ログにいつでもアクセスできます。 詳細については、「ログ記録と [Azure Rights Management Usage の分析」を参照してください](/azure/information-protection/log-analyze-usage)。

Azure Rights Management は、ワイヤー タップ、中間者攻撃、データ盗難、組織共有ポリシーの意図しない違反などの脅威を軽減します。 同時に、適切なアクセス許可を持つ承認されていないユーザーによる、転送中または保存中の顧客データへの不正なアクセスは、そのデータに従うポリシーを介して防止され、そのデータが故意または無意識のうちに誤った手に落ちて、データ損失防止機能を提供するリスクを軽減します。 Azure Information Protection の一部として使用される場合、Azure RMS には、データ分類とラベル付け機能、コンテンツ マーキング、ドキュメント アクセス追跡、アクセス取り消し機能も提供されます。 これらの機能の詳細については [、「What is Azure Information Protection、Azure Information Protection](/information-protection/understand-explore/what-is-information-protection)展開ロードマップ、 [および](/information-protection/plan-design/deployment-roadmap)Azure Information Protection のクイック スタート チュートリアル」 [を参照してください](/information-protection/get-started/infoprotect-quick-start-tutorial)。

## <a name="secure-multipurpose-internet-mail-extension"></a>Secure Multipurpose Internet Mail Extension

Secure/Multipurpose Internet Mail Extensions (S/MIME) は、公開キーの暗号化と MIME データのデジタル署名の標準です。 S/MIME は RFC 3369、3370、3850、3851 などで定義されます。 これにより、ユーザーは電子メールを暗号化し、電子メールにデジタル署名できます。 S/MIME を使用して暗号化された電子メールは、秘密キーを使用して電子メールの受信者によってのみ解読できます。これは、その受信者だけが使用できます。 そのため、電子メールの受信者以外のユーザーが電子メールを解読することはできません。

[Microsoft は S/MIME をサポートしています](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)。 パブリック証明書は、顧客のオンプレミス Active Directory に配布され、テナントにレプリケートできる属性Microsoft 365されます。 公開キーに対応するプライベート キーはオンプレミスのままで、パブリック キーにOffice 365。 ユーザーは、Outlook、Outlook on the web、および Exchange ActiveSync クライアントを使用して、組織内の 2 人のユーザー間で電子メールを作成、暗号化、復号化、読み取り、およびデジタル署名できます。 詳細については、「S/MIME 暗号化」[を参照Office 365。](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)

## <a name="office-365-message-encryption"></a>Office 365 Message Encryption

[Office 365 Message Encryption](https://products.office.com/exchange/office-365-message-encryption) (AIP) の上に構築された OME[を使用](/information-protection/understand-explore/what-is-information-protection)すると、暗号化された権限で保護されたメールを誰にでも送信できます。 OME は、ワイヤー タップ攻撃や中間者攻撃などの脅威や、適切なアクセス許可を持たない承認されていないユーザーによるデータへの不正アクセスなど、その他の脅威を軽減します。 Azure Information Protection の上に構築された、よりシンプルで直感的で安全な電子メール エクスペリエンスを提供する投資を行いました。 組織の内部または外部Microsoft 365に送信されるメッセージを保護できます。 これらのメッセージは、ユーザー ID、Microsoft アカウント、Google ID など、任意の id を使用して、さまざまなメール クライアントAzure Active Directory表示できます。 組織で暗号化されたメッセージを使用する方法の詳細については、「Office 365 Message Encryption」[を参照してください](./ome.md)。

## <a name="transport-layer-security"></a>トランスポート層セキュリティ   

パートナーとの安全な通信を確保する場合は、受信コネクタと送信コネクタを使用して、セキュリティとメッセージの整合性を提供できます。 証明書を使用して、各コネクタで強制的な受信および送信 TLS を構成できます。 暗号化された SMTP チャネルを使用すると、中間者攻撃によってデータが盗まれるのを防ぐ可能性があります。 詳細については、「TLS を使用[して電子メールExchange Onlineセキュリティで保護する方法」を参照してください](./exchange-online-uses-tls-to-secure-email-connections.md)。

## <a name="domain-keys-identified-mail"></a>ドメイン キー識別メール

Exchange Online Protection (EOP) Exchange Onlineドメイン キー識別メール (DKIM) メッセージの受信検証をサポートします。 DKIM は、メッセージが発信元であり、他のユーザーによってスプーフィングされていないというメッセージがドメインから送信されたと検証するためのメソッドです。 電子メール メッセージは、送信を担当する組織に結び付け、電子メール暗号化の大きなパラダイムの一部です。 このパラダイムの 3 つの部分の詳細については、以下を参照してください。

- [SPF を設定して、スプーフィングを防止する](/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する](/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [DMARC を使用してメールを検証する](/office365/SecurityCompliance/use-dmarc-to-validate-email)