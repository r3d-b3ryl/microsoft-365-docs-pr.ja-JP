---
title: Azure での暗号化
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
description: Azure Disk Encryption など、Azure で使用できる暗号化について説明します
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de0e98feb54cd2f56ebea35a0f0ec243b8712d86
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67472438"
---
# <a name="encryption-in-azure"></a>Azure での暗号化

暗号化された通信や運用プロセスなど、Azure の技術的な保護は、データのセキュリティを維持するのに役立ちます。 また、追加の暗号化機能を実装し、独自の暗号化キーを管理する柔軟性もあります。 Microsoft は、お客様の構成に関係なく、Azure の顧客データを保護するために暗号化を適用します。 Microsoft では、暗号化キーの暗号化、制御、管理、データへのアクセスの制御と監査を行う高度なテクノロジを通じて、Azure でホストされているデータを制御することもできます。 さらに、Azure Storage には、開発者がセキュリティで保護されたアプリケーションを構築できる包括的な一連のセキュリティ機能が用意されています。

Azure には、ある場所から別の場所に移動する際にデータを保護するための多くのメカニズムが用意されています。 Microsoft は TLS を使用して、クラウド サービスと顧客の間を移動するときにデータを保護します。 Microsoft のデータ センターは、Azure サービスに接続するクライアント システムとの TLS 接続をネゴシエートします。 Perfect Forward Secrecy (PFS) は、お客様のクライアント システムと Microsoft のクラウド サービス間の接続を一意のキーで保護します。 接続では、RSA ベースの 2,048 ビット暗号化キーの長さも使用されます。 この組み合わせにより、転送中のデータを傍受してアクセスすることが困難になります。

[クライアント側の暗号化](/azure/storage/storage-client-side-encryption)、HTTPS、または SMB 3.0 を使用して、アプリケーションと Azure 間の転送中にデータをセキュリティで保護できます。 独自の仮想マシン (VM) とユーザー間のトラフィックの暗号化を有効にすることができます。 [Azure Virtual Networks](https://azure.microsoft.com/services/virtual-network/) では、業界標準の IPsec プロトコルを使用して、企業の VPN ゲートウェイと Azure の間、およびVirtual Networkにある VM 間のトラフィックを暗号化できます。

保存データの場合、Azure には AES-256 のサポートなど、多くの暗号化オプションが用意されています。これにより、ニーズに最も適したデータ ストレージ シナリオを柔軟に選択できます。 [Storage Service](/azure/storage/storage-service-encryption) Encryption を使用して Azure Storage に書き込むと、データを自動的に暗号化でき、VM で使用されるオペレーティング システムとデータ ディスクを暗号化できます。 詳細については、「 [Azure での Windows 仮想マシンのセキュリティに関する推奨事項」を](/azure/virtual-machines/security-recommendations)参照してください。 さらに、 [共有アクセス署名](/azure/storage/storage-dotnet-shared-access-signature-part-1)を使用して、Azure Storage 内のデータ オブジェクトへの委任されたアクセスを許可できます。 Azure では、Azure SQL [データベースとData Warehouse用の Transparent Data Encryption](/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql) を使用して保存データの暗号化も提供されます。

Azure での暗号化の詳細については、 [Azure 暗号化の概要](/azure/security/security-azure-encryption-overview) と [Azure Data Encryption-at-Rest](/azure/security/azure-security-encryption-atrest) に関するページを参照してください。

## <a name="azure-disk-encryption"></a>Azure Disk Encryption

Azure Disk Encryption を使用すると、Windows および Linux インフラストラクチャ as a Service (IaaS) VM ディスクを暗号化できます。 Azure Disk Encryption は、Windows の BitLocker 機能と Linux のDM-Crypt機能を利用して、オペレーティング システムとデータ ディスクにボリューム レベルの暗号化を提供します。 また、VM ディスク上のすべてのデータが Azure ストレージ内の保存時に暗号化されるようにすることもできます。 Azure Disk Encryption は Azure Key Vaultと統合されており、暗号化キーとシークレットの使用を制御、管理、監査するのに役立ちます。

詳細については、「 [Azure での Windows 仮想マシンのセキュリティに関する推奨事項」を](/azure/virtual-machines/windows/security-recommendations)参照してください。

## <a name="azure-storage-service-encryption"></a>Azure Storage サービス暗号化

[Azure Storage Service Encryption](/azure/storage/storage-service-encryption) を使用すると、Azure Storage はデータをストレージに永続化する前に自動的に暗号化し、取得前にデータを復号化します。 暗号化、復号化、およびキー管理プロセスは、ユーザーに対して完全に透過的です。 Azure Storage Service Encryption は[、Azure Blob Storage](https://azure.microsoft.com/services/storage/blobs/)と[Azure Files](https://azure.microsoft.com/services/storage/files/)に使用できます。 Azure Storage Service Encryption で Microsoft マネージド暗号化キーを使用することも、独自の暗号化キーを使用することもできます。 (独自のキーの使用については、「[Azure Key Vaultのカスタマー マネージド キーを使用した Storage Service Encryption](/azure/storage/common/storage-service-encryption-customer-managed-keys)」を参照してください。 Microsoft マネージド キーの使用の詳細については、「 [Storage Service Encryption for Data at Rest](/azure/storage/storage-service-encryption)」を参照してください)。さらに、暗号化の使用を自動化することもできます。 たとえば、[Azure Storage Resource Provider REST API](/rest/api/storagerp/)、[.NET 用](/dotnet/api/overview/azure/storage)ストレージ リソース プロバイダー クライアント ライブラリ、Azure PowerShell、または [Azure CLI](/azure/storage/storage-azure-cli) を使用して、ストレージ アカウントで Storage Service Encryption をプログラム[で](/powershell/azureps-cmdlets-docs)有効または無効にすることができます。

一部の Microsoft 365 サービスでは、データを格納するために Azure が使用されます。 たとえば、SharePoint Online とOneDrive for Businessは Azure Blob Storage にデータを格納し、Microsoft Teams はチャット サービスのデータをテーブル、BLOB、キューに格納します。 さらに、Microsoft Purview コンプライアンス ポータルのコンプライアンス マネージャー機能には、Azure [Cosmos DB](/azure/cosmos-db/database-encryption-at-rest) (サービスとしてのプラットフォーム (PaaS) の暗号化された形式で格納される顧客が入力したデータが格納されます。グローバルに分散されたマルチモデル データベースです。 Azure Storage Service Encryption は Azure Blob Storage とテーブルに格納されたデータを暗号化し、Azure Disk Encryption はキュー内のデータと Windows および IaaS 仮想マシン ディスクを暗号化して、オペレーティング システムとデータ ディスクのボリューム暗号化を提供します。 このソリューションにより、仮想マシン ディスク上のすべてのデータが Azure ストレージ内の保存時に暗号化されます。 [Azure Cosmos DB の保存時の暗号化](/azure/cosmos-db/database-encryption-at-rest) は、セキュリティで保護されたキー ストレージ システム、暗号化されたネットワーク、暗号化 API など、いくつかのセキュリティ テクノロジを使用して実装されます。

## <a name="azure-key-vault"></a>Azure Key Vault

セキュリティで保護されたキー管理は、暗号化のベスト プラクティスの中核だけではありません。また、クラウド内のデータを保護するためにも不可欠です。 [Azure Key Vault](/azure/key-vault/key-vault-whatis)を使用すると、ハードウェア セキュリティ モジュール (HSM) に格納されているキーを使用するキーやパスワードなどの小さなシークレットを暗号化できます。 Azure Key Vaultは、クラウド サービスで使用される暗号化キーへのアクセスを管理および制御するための Microsoft のお勧めのソリューションです。 キーにアクセスするためのアクセス許可は、サービスまたは Azure Active Directory アカウントを持つユーザーに割り当てることができます。 Azure Key Vaultでは、HSM とキー管理ソフトウェアを構成、修正プログラム、保守する必要が組織から軽減されます。 Azure Key Vaultを使用すると、Microsoft はキーやアプリケーションに直接アクセスできないことを確認せず、制御を維持します。 HSM でキーをインポートまたは生成することもできます。 Azure Information Protectionを含むサブスクリプションを持つ組織は、カスタマー マネージド キー Bring [Your Own Key](/information-protection/plan-design/byok-price-restrictions) (BYOK) を使用するように Azure Information Protection テナントを構成し、[その使用状況をログに記録](/information-protection/deploy-use/log-analyze-usage)できます。
