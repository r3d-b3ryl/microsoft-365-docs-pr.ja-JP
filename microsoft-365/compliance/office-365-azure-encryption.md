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
description: Azure で使用可能な暗号化 (Azure ディスク暗号化など) について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f3672800b6f90277195a63b640911ea1ed24cac9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152949"
---
# <a name="encryption-in-azure"></a>Azure での暗号化

暗号化された通信や運用プロセスなど、Azure の技術的な保護措置は、データのセキュリティ保護に役立ちます。 また、追加の暗号化機能を実装し、独自の暗号化キーを管理することもできます。 お客様の構成に関係なく、Microsoft は暗号化を適用して Azure の顧客データを保護します。 Microsoft では、暗号化キーの暗号化、制御、管理、およびデータへのアクセスの制御と監査を行うさまざまな高度なテクノロジを通じて、Azure でホストされるデータを制御することもできます。 さらに、Azure Storageは、開発者がセキュリティで保護されたアプリケーションを構築できる包括的なセキュリティ機能のセットを提供します。

Azure には、データをある場所から別の場所に移動する場合に、データを保護するための多くのメカニズムが用意されています。 Microsoft は、クラウド サービスと顧客の間を移動する際に TLS を使用してデータを保護します。 Microsoft のデータ センターは、Azure サービスに接続するクライアント システムとの TLS 接続をネゴシエートします。 Perfect Forward Secrecy (PFS) は、お客様のクライアント システムと Microsoft のクラウド サービス間の接続を一意のキーで保護します。 接続では、RSA ベースの 2,048 ビット暗号化キーの長さも使用します。 この組み合わせにより、転送中のデータを傍受してアクセスすることは困難になります。

クライアント側の暗号化、HTTPS、または SMB 3.0 を使用して、アプリケーションと Azure 間の転送中にデータをセキュリティで保護できます。 [](/azure/storage/storage-client-side-encryption) 独自の仮想マシン (VM) とユーザー間のトラフィックの暗号化を有効にできます。 [Azure Virtual Networks を](https://azure.microsoft.com/services/virtual-network/)使用すると、業界標準の IPsec プロトコルを使用して、企業の VPN ゲートウェイと Azure の間、および仮想ネットワーク上にある VM 間のトラフィックを暗号化できます。

保存中のデータの場合、Azure には AES-256 のサポートなど、多くの暗号化オプションが用意されています。ニーズに最適なデータ ストレージ シナリオを柔軟に選択できます。 Azure Storage Service [Encryption](/azure/storage/storage-service-encryption)を使用して Azure StorageにStorageデータを自動的に暗号化し、VM で使用されるオペレーティング システムとデータ ディスクを暗号化できます。 詳細については[、「Azure の仮想マシンのセキュリティWindows」を参照してください](/azure/security/azure-security-disk-encryption)。 さらに、共有アクセス署名を使用して、Azure Storageデータ オブジェクトへの委任[されたアクセスを許可できます](/azure/storage/storage-dotnet-shared-access-signature-part-1)。 Azure では、データ ウェアハウスとデータ ウェアハウスに対するTransparent Data Encryption[をAzure SQL Databaseデータの暗号化も提供します](/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)。

Azure での暗号化の詳細については、「Azure [暗号化](/azure/security/security-azure-encryption-overview) の概要」および [「Azure Data Encryption-at-Rest」を参照してください](/azure/security/azure-security-encryption-atrest)。

## <a name="azure-disk-encryption"></a>Azure ディスクの暗号化

Azure Disk Encryption を使用すると、Windows Linux Infrastructure as a Service (IaaS) VM ディスクを暗号化できます。 Azure Disk Encryption は、Windows の BitLocker 機能と Linux の DM-Crypt 機能を活用して、オペレーティング システムとデータ ディスクのボリューム レベルの暗号化を提供します。 また、VM ディスク上のすべてのデータが Azure ストレージの保存時に暗号化されます。 Azure Disk Encryption は Azure Key Vault と統合され、暗号化キーとシークレットの使用を制御、管理、監査するのに役立ちます。

詳細については[、「Azure の仮想マシンのセキュリティWindows」を参照してください](/azure/virtual-machines/windows/security-recommendations)。

## <a name="azure-storage-service-encryption"></a>Azure Storageサービスの暗号化

サービス[Azure Storageでは](/azure/storage/storage-service-encryption)、Azure Storage保存する前にデータを自動的に暗号化し、取得前にデータを復号化します。 暗号化、復号化、およびキー管理プロセスは、ユーザーに対して完全に透過的です。 Azure Storageサービス暗号化は、Azure BLOB ファイルおよび[Azure ファイルStorage](https://azure.microsoft.com/services/storage/blobs/)[使用できます](https://azure.microsoft.com/services/storage/files/)。 Microsoft が管理する暗号化キーをサービス暗号化とAzure Storage、独自の暗号化キーを使用することもできます。 (独自のキーの使用の詳細については[、「Azure Key Vault Storageを](/azure/storage/common/storage-service-encryption-customer-managed-keys)使用したサービス暗号化」を参照してください。 Microsoft 管理キーの使用の詳細については、「Storageデータの暗号化 」[を参照](/azure/storage/storage-service-encryption)してください。さらに、暗号化の使用を自動化できます。 [たとえば](/powershell/azureps-cmdlets-docs)、Azure Storage リソース プロバイダー [REST API、.NET、Azure PowerShell、](/rest/api/storagerp/)または Azure CLI の[Storage](/dotnet/api/overview/azure/storage)リソース プロバイダー クライアント ライブラリを使用して、ストレージ アカウントで Storage サービス暗号化をプログラムで有効または無効に[できます](/azure/storage/storage-azure-cli)。

一部Microsoft 365サービスは、データの格納に Azure を使用します。 たとえば、SharePointおよび OneDrive for Businessは Azure BLOB ストレージにデータを格納し、Microsoft Teams はチャット サービスのデータをテーブル、BLOB、キューに格納します。 さらに、Microsoft 365 コンプライアンス センター のコンプライアンス マネージャー機能は[、Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest)、サービスとしてのプラットフォーム (PaaS)、グローバルに分散されたマルチモデル データベースに暗号化された形式で格納される顧客入力データを格納します。 Azure Storageサービス暗号化は、Azure BLOB ストレージとテーブルに格納されたデータを暗号化し、Azure Disk Encryption はキュー内のデータと、Windows および IaaS 仮想マシン ディスクを暗号化して、オペレーティング システムとデータ ディスクのボリューム暗号化を提供します。 このソリューションにより、仮想マシン ディスク上のすべてのデータが Azure ストレージの保存時に暗号化されます。 Azure Cosmos DB の保存時の暗号化は[、セキュリティで保護](/azure/cosmos-db/database-encryption-at-rest)されたキー ストレージ システム、暗号化されたネットワーク、暗号化 API など、いくつかのセキュリティ テクノロジを使用して実装されます。

## <a name="azure-key-vault"></a>Azure Key Vault

セキュリティで保護されたキー管理は、暗号化のベスト プラクティスのコアではありません。また、クラウド内のデータを保護するためにも重要です。 [Azure Key Vault](/azure/key-vault/key-vault-whatis) を使用すると、ハードウェア セキュリティ モジュール (HSM) に格納されているキーを使用するパスワードなど、キーや小さなシークレットを暗号化できます。 Azure Key Vault は、クラウド サービスで使用される暗号化キーへのアクセスを管理および制御するための Microsoft の推奨ソリューションです。 キーにアクセスするためのアクセス許可は、サービスまたはアカウントを持つユーザー Azure Active Directoryできます。 Azure Key Vault を使用すると、組織は、HSM とキー管理ソフトウェアを構成、修正、保守する必要が軽減されます。 Azure Key Vault を使用すると、Microsoft ではキーが表示され、アプリケーションはキーに直接アクセスすることはできません。コントロールを維持します。 また、HSM でキーをインポートまたは生成することもできます。 Azure Information Protection を含むサブスクリプションを持つ組織は、顧客管理キー [Bring Your Own Key](/information-protection/plan-design/byok-price-restrictions) (BYOK) を使用するように Azure Information Protection テナントを構成し、その使用状況を [ログに記録できます](/information-protection/deploy-use/log-analyze-usage)。