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
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: この記事では、Microsoft クラウドで顧客データを安全に保つために使用されるさまざまな形式の暗号化の概要について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a253f5fb0df4f71c47aa0c64bd5bfb48ef874c2b1de4d92de245bb2962c3dc7e
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53807734"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft Cloud での暗号化

Microsoft のエンタープライズ クラウド サービス内の顧客データは、さまざまな形式の暗号化を含むいくつかのテクノロジとプロセスによって保護されています。 (このドキュメントの顧客データには、Exchange Online メールボックスコンテンツ、電子メール本文、予定表エントリ、電子メール添付ファイルのコンテンツ、および該当する場合は Skype for Business コンテンツ)、SharePoint Online サイトコンテンツとサイト内に保存されているファイル、および OneDrive for Business または Skype for Business にアップロードされたファイルが含まれます)。Microsoft は、製品およびサービス全体で複数の暗号化方法、プロトコル、および暗号を使用して、お客様のデータがクラウド サービスを通過するための安全なパスを提供し、クラウド サービス内に保存されている顧客データの機密性を保護するのに役立ちます。 Microsoft は、お客様のデータへの不正アクセスに対する障壁を提供するために、利用可能な最も強力で最も安全な暗号化プロトコルの一部を使用しています。 適切なキー管理は、暗号化のベスト プラクティスにも不可欠な要素であり、Microsoft は、すべての Microsoft で管理される暗号化キーが適切に保護されていることを確認します。

Microsoft のエンタープライズ クラウド サービス内に格納されている顧客データは、1 つ以上の形式の暗号化を使用して保護されます。 (暗号化ポリシーとその適用の検証は、複数のサード パーティ監査者によって個別に検証され、これらの監査のレポートは [サービス信頼](https://aka.ms/stp)ポータルで確認できます。)

Microsoft は、お客様のデータを保存時および転送中に暗号化するサービス側テクノロジを提供しています。 たとえば、保存中の顧客データの場合、Microsoft Azure は[BitLocker](/windows/device-security/bitlocker/bitlocker-overview)と[DM-Crypt](https://en.wikipedia.org/wiki/Dm-crypt)を使用し、Microsoft 365 は BitLocker、Azure Storage サービス暗号化、分散キー マネージャー (DKM)、および Microsoft 365 サービス暗号化を使用します。 [](/azure/) [](./exchange-online-secures-email-secrets.md) 転送中の顧客データの場合、Azure、Office 365、Microsoft Commercial Support、Microsoft Dynamics 365、Microsoft Power BI、および Visual Studio Team Services は、Microsoft データセンター間、およびユーザー デバイスと Microsoft データセンター間で、インターネット プロトコル セキュリティ (IPsec) やトランスポート層セキュリティ (TLS) などの業界標準のセキュリティで保護されたトランスポート プロトコルを使用します。

Microsoft が提供する暗号化セキュリティのベースライン レベルに加えて、クラウド サービスには、管理できる暗号化オプションも含まれます。 たとえば、Azure 仮想マシン (VM) とそのユーザー間のトラフィックの暗号化を有効にできます。 [Azure Virtual Networks を使用](https://azure.microsoft.com/services/virtual-network/)すると、業界標準の IPsec プロトコルを使用して、企業の VPN ゲートウェイと Azure 間のトラフィックを暗号化できます。 仮想ネットワーク上の VM 間のトラフィックを暗号化できます。 さらに、[新しいOffice 365 Message Encryption機能を使用](set-up-new-message-encryption-capabilities.md)すると、暗号化されたメールを誰にでも送信できます。

Microsoft セキュリティ ポリシーのコンポーネントである公開キー インフラストラクチャの運用セキュリティ標準に従って[、Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)は証明書と認証メカニズムのために Windows オペレーティング システムに含まれる暗号化機能を使用します。 これらのメカニズムには、米国政府の連邦情報処理標準[](https://csrc.nist.gov/publications/PubsFIPS.html) (FIPS) 140-2 標準を満たす暗号化モジュールの使用が含まれます。 暗号化モジュール検証プログラム CMVP を使用して、Microsoft の関連する NIST 証明書番号 [を検索できます](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search)。

> [メモ]リソースとして Microsoft セキュリティ ポリシーにアクセスするには、仕事用または学校用のアカウントを使用してサインインする必要があります。 サブスクリプションがまだない場合は、 [無料試用版にサインアップできます](https://servicetrust.microsoft.com/Home/TrialSubscriptions)。

FIPS 140-2 は、暗号化を実装する製品モジュールを使用する製品ではなく、検証用に特別に設計された標準です。 サービス内に実装される暗号化モジュールは、ハッシュ強度、キー管理などの要件を満たしていることを認定できます。 Microsoft のクラウド サービスのデータの機密性、整合性、または可用性を保護するために使用される暗号化モジュールと暗号は、FIPS 140-2 標準を満たしています。

Microsoft は、クラウド サービスで使用される基になる暗号化モジュールを、クラウド オペレーティング システムの新しいリリースごとにWindowsします。

- Azure と Azure の米国政府機関
- Dynamics 365、Dynamics 365 米国政府
- Office 365、Office 365 米国政府、Office 365 米国防総省

保存中の顧客データの暗号化は、BitLocker、DKM、Azure Storage サービス暗号化、Exchange Online、Skype for Business、OneDrive for Business、および SharePoint Online のサービス暗号化など、複数のサービス側テクノロジによって提供されます。 Office 365には、Azure Key Vault に格納されている顧客管理の暗号化キーを使用するオプションが含まれています。 顧客キーと呼ばれるこの顧客管理キー[](./customer-key-overview.md)オプションは、Exchange Online、SharePoint Online、Skype for Business、およびOneDrive for Business。

転送中の顧客データの場合、すべてのサーバー Office 365クライアント コンピューターと TLS を使用してセキュリティで保護されたセッションをネゴシエートして、顧客データを保護します。 たとえば、Office 365は、セキュリティで保護されたセッションSkype for Business、Outlook、Outlook on the web、および Web ブラウザーにネゴシエートします。

(すべての顧客向けサーバーは、既定で TLS 1.2 とネゴシエートします)。

## <a name="related-links"></a>関連リンク

- [Azure での暗号化](office-365-azure-encryption.md)
- [BitLocker とDistributed Key Manager (DKM) による暗号化](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 でのサービスの暗号化](office-365-service-encryption.md)
- [Office 365オンライン、Skype for Business、OneDrive for Business、SharePointの暗号化Exchange Online](/compliance/assurance/assurance-encryption-for-microsoft-365-services) 
- [転送中データの暗号化](/compliance/assurance/assurance-encryption-in-transit)
- [顧客により管理される暗号化機能](office-365-customer-managed-encryption-features.md)
- [暗号化のリスクと保護](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365 での暗号化](office-365-encryption-in-microsoft-dynamics-365.md)