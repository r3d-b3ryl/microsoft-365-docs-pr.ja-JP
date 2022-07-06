---
title: Microsoft Cloud での暗号化
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
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: この記事では、Microsoft クラウドで顧客データを安全に保つために使用されるさまざまな形式の暗号化の概要について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3105da5d17b1656ffa0d29da4f4aa02c9a9f9064
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633919"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft Cloud での暗号化

Microsoft のエンタープライズ クラウド サービス内の顧客データは、さまざまな形式の暗号化を含むいくつかのテクノロジとプロセスによって保護されています。 (このドキュメントの顧客データには、Exchange Onlineメールボックスコンテンツ、電子メール本文、予定表エントリ、電子メールの添付ファイルのコンテンツ、および該当する場合はSkype for Businessコンテンツ)、SharePoint Online サイトコンテンツ、サイト内に保存されているファイル、およびOneDrive for BusinessまたはSkype for Business.)Microsoft は、製品とサービス全体で複数の暗号化方法、プロトコル、暗号を使用して、お客様のデータがクラウド サービスを通過するための安全なパスを提供し、クラウド サービス内に格納されている顧客データの機密性を保護するのに役立ちます。 Microsoft では、お客様のデータへの不正アクセスに対する障壁を提供するために、最も強力で最も安全な暗号化プロトコルの一部を使用しています。 適切なキー管理は、暗号化のベスト プラクティスの不可欠な要素でもあります。Microsoft は、Microsoft が管理するすべての暗号化キーが適切にセキュリティで保護されるように努めています。

Microsoft のエンタープライズ クラウド サービス内に格納されている顧客データは、1 つ以上の形式の暗号化を使用して保護されます。 (暗号化ポリシーとその適用の検証は、複数のサード パーティの監査者によって独立して検証され、それらの監査のレポートは [Service Trust Portal](https://aka.ms/stp) で入手できます)。

Microsoft は、保存時および転送中の顧客データを暗号化するサービス側テクノロジを提供しています。 たとえば、保存データの場合、Microsoft Azure では [BitLocker](/windows/device-security/bitlocker/bitlocker-overview) と [DM-Crypt](https://en.wikipedia.org/wiki/Dm-crypt) が使用され、Microsoft 365 では BitLocker、 [Azure Storage Service Encryption](/azure/)、 [Distributed Key Manager](./exchange-online-secures-email-secrets.md) (DKM)、Microsoft 365 サービス暗号化が使用されます。 転送中の顧客データの場合、Azure、Office 365、Microsoft Commercial Support、Microsoft Dynamics 365、Microsoft Power BI、Visual Studio Team Servicesでは、Microsoft データセンター間、ユーザー デバイスと Microsoft データセンターの間で、インターネット プロトコル セキュリティ (IPsec) やトランスポート層セキュリティ (TLS) などの業界標準のセキュリティで保護されたトランスポート プロトコルが使用されます。

Microsoft によって提供される暗号化セキュリティのベースライン レベルに加えて、クラウド サービスには、管理できる暗号化オプションも含まれています。 たとえば、Azure 仮想マシン (VM) とそのユーザー間のトラフィックの暗号化を有効にすることができます。 [Azure Virtual Networks](https://azure.microsoft.com/services/virtual-network/) では、業界標準の IPsec プロトコルを使用して、企業 VPN ゲートウェイと Azure 間のトラフィックを暗号化できます。 仮想ネットワーク上の VM 間のトラフィックを暗号化することもできます。 さらに、[新しいOffice 365メッセージ暗号化機能](set-up-new-message-encryption-capabilities.md)を使用すると、暗号化されたメールをだれにでも送信できます。

[Microsoft セキュリティ ポリシー](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)のコンポーネントである公開キー インフラストラクチャ運用セキュリティ標準に従って、Microsoft は証明書と認証メカニズムに Windows オペレーティング システムに含まれる暗号化機能を使用します。 これらのメカニズムには、米国政府の [連邦情報処理標準](https://csrc.nist.gov/publications/PubsFIPS.html) (FIPS) 140-2 標準を満たす暗号化モジュールの使用が含まれます。 [暗号化モジュール検証プログラム CMVP](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search) を使用して、Microsoft の関連する NIST 証明書番号を検索できます。

> [注]リソースとして Microsoft セキュリティ ポリシーにアクセスするには、職場または学校のアカウントを使用してサインインする必要があります。 サブスクリプションがまだない場合は、 [無料試用版にサインアップできます](https://servicetrust.microsoft.com/Home/TrialSubscriptions)。

FIPS 140-2 は、それらを使用する製品ではなく、暗号化を実装する製品モジュールを検証するために特別に設計された標準です。 サービス内で実装される暗号化モジュールは、ハッシュ強度、キー管理などの要件を満たすものとして認定できます。 Microsoft のクラウド サービスのデータの機密性、整合性、または可用性を保護するために使用される暗号化モジュールと暗号は、FIPS 140-2 標準を満たしています。

Microsoft は、Windows オペレーティング システムの新しいリリースごとに、クラウド サービスで使用される基になる暗号化モジュールを認定します。

- Azure と Azure の米国政府機関
- Dynamics 365、Dynamics 365 米国政府
- Office 365、Office 365 米国政府、Office 365 米国防総省

保存時の顧客データの暗号化は、BitLocker、DKM、Azure Storage Service Encryption、Exchange Online、Skype for Business、OneDrive for Business、SharePoint Online でのサービス暗号化など、複数のサービス側テクノロジによって提供されます。 Office 365サービス暗号化には、Azure Key Vaultに格納されているカスタマー マネージド暗号化キーを使用するオプションが含まれています。 カスタマー キーと呼ばれるこのカスタマー マネージド [キー](./customer-key-overview.md) オプションは、Exchange Online、SharePoint Online、Skype for Business、OneDrive for Businessで使用できます。

転送中の顧客データの場合、すべてのOffice 365 サーバーは、クライアント コンピューターと TLS を使用してセキュリティで保護されたセッションをネゴシエートし、顧客データをセキュリティで保護します。 たとえば、Office 365は、Skype for Business、Outlook、Outlook on the web、モバイル クライアント、Web ブラウザーへのセキュリティで保護されたセッションをネゴシエートします。

(既定では、すべての顧客向けサーバーが TLS 1.2 にネゴシエートします)。

## <a name="related-links"></a>関連リンク

- [Azure での暗号化](office-365-azure-encryption.md)
- [BitLocker とDistributed Key Manager (DKM) による暗号化](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 でのサービスの暗号化](office-365-service-encryption.md)
- [Skype for Business、OneDrive for Business、SharePoint Online、およびExchange OnlineのOffice 365暗号化](/compliance/assurance/assurance-encryption-for-microsoft-365-services) 
- [転送中データの暗号化](/compliance/assurance/assurance-encryption-in-transit)
- [顧客により管理される暗号化機能](office-365-customer-managed-encryption-features.md)
- [暗号化のリスクと保護](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365 での暗号化](office-365-encryption-in-microsoft-dynamics-365.md)
