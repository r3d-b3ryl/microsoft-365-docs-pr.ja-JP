---
title: Microsoft Dynamics 365 での暗号化
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
description: Microsoft が暗号化テクノロジを使用して Microsoft Dynamics 365 の顧客データを保護する方法について説明します。Microsoft データベース内および転送中に保存中。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22ac316240b0bf299351c48eef876d456662b23e4a856905ebdd92829c41a182
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53885545"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365 での暗号化

Microsoft では、暗号化テクノロジを使用して、ユーザー デバイスとデータセンター間の転送中に、Dynamics 365 の顧客データを保護します。 顧客と Microsoft データセンター間で確立された接続は暗号化され、すべてのパブリック エンドポイントは業界標準の TLS を使用してセキュリティで保護されます。 TLS は、セキュリティが強化されたブラウザー間接続を効果的に確立し、デスクトップとデータセンター間のデータの機密性と整合性を確保します。 データ暗号化をアクティブ化した後は、オフにすることはできません。 詳細については、「フィールド レベル [のデータ暗号化」を参照してください](/previous-versions/dynamicscrm-2016/developers-guide/dn481562(v=crm.8))。

Dynamics 365 はMicrosoft SQL Server、ユーザー名や電子メール パスワードなどの機密情報を含む一連の既定のエンティティ属性に対して、標準のセル レベルの暗号化を使用します。 この機能は、組織が FIPS 140-2 に関連するコンプライアンス要件を満たすのに役立ちます。 フィールド レベルのデータ暗号化は[、Dynamics](/previous-versions/dynamicscrm-2016/administering-dynamics-365/hh699800(v=crm.8))365 インスタンスと電子メール サービスの統合を可能にするには、ユーザー名とパスワードを保存する必要がある Microsoft Dynamics CRM メール ルーターを活用するシナリオで特に重要です。

Dynamics 365[のすべての](/sql/relational-databases/security/encryption/transparent-data-encryption)インスタンスは、Microsoft SQL Server Transparent Data Encryption (TDE) を使用して、ディスクに書き込まれたときにデータのリアルタイム暗号化を実行します (保存時)。 TDE は、SQL Server、Azure SQL Database、Azure データ ウェアハウスSQLファイルを暗号化します。 既定では、Microsoft は Dynamics 365 のインスタンスのデータベース暗号化キーを格納および管理します。 (Dynamics 365 for Financials で使用されるキーは、データ保護 API によって.NET Frameworkされます。

Dynamics 365 管理センターのキーの管理機能により、管理者は Dynamics 365 のインスタンスに関連付けられているデータベース暗号化キーを自己管理できます。 (自己管理データベース暗号化キーは、Microsoft Dynamics 365 の 2017 年 1 月の更新プログラムでのみ使用できます。以降のバージョンでは使用できない場合があります。 詳細については [、「Dynamics 365 (online)](/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)インスタンスの暗号化キーを管理する」を参照してください。キー管理機能は、PFX と BYOK の両方の暗号化キー ファイル (HSM に格納されているファイルなど) をサポートします。 (インターネットを使用した HSM で保護されたキーの生成と転送の詳細については [、「Azure Key Vault](/azure/key-vault/key-vault-hsm-protected-keys)の HSM で保護されたキーを生成および転送する方法」を参照してください。

[暗号化キーのアップロード] オプションを使用するには、パブリック暗号化キーとプライベート暗号化キーの両方が必要です。

キー管理機能は、Azure Key Vault を使用して暗号化キーを安全に格納することで、暗号化キー管理の複雑さを取り出します。 Azure Key Vault は、クラウド アプリケーションとサービスで使用される暗号化キーとシークレットを保護するのに役立ちます。 キー管理機能では、Azure Key Vault サブスクリプションを使用する必要はありません。ほとんどの場合、コンテナー内の Dynamics 365 で使用される暗号化キーにアクセスする必要はありません。