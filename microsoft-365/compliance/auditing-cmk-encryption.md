---
title: カスタマー マネージド キーを使用して組織の監査データを暗号化する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- m365-security-compliance
search.appverid:
- MOE150
- MET150
description: カスタマー マネージド キーを使用して組織の監査レコードを暗号化する方法について説明します。
ms.openlocfilehash: afbae48b0417c42edd7e14220fb21f6402af1da7
ms.sourcegitcommit: e0f890f46ae0bde03cc9e1ce178a7c1b8fbe12db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2022
ms.locfileid: "65145424"
---
# <a name="use-customer-key-to-encrypt-audit-records"></a>顧客キーを使用して監査レコードを暗号化する

これで、監査レコードに対して Microsoft Purview カスタマー キー暗号化を有効にできるようになりました。 監査は、 [Microsoft Purview カスタマー キーを使用したサービス暗号化](customer-key-overview.md) に基づいて構築され、組織の監査データを暗号化します。 カスタマー キーを実装すると、承認されていないシステムまたは Microsoft データ センターの担当者が監査パイプラインと保存時に監査データを表示できないようにすることで、保護が強化されます。 顧客キーを使用して監査データを暗号化すると、組織が暗号化キーを提供および制御するため、規制またはコンプライアンスの義務を満たすのにも役立ちます。

カスタマー キーには、Microsoft 365 E5 サブスクリプションが必要です。 詳細については、[セキュリティ&コンプライアンスに関するMicrosoft 365ガイダンスを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-customer-key-for-microsoft-365)参照してください。

カスタマー キーを使用して監査レコードを暗号化しない場合でも、Microsoft 365の保存データは既定で暗号化されます。

## <a name="implement-customer-key-for-auditing"></a>監査用のカスタマー キーを実装する

監査用のカスタマー キーを実装するには、暗号化階層を定義するマルチワークロード データ暗号化ポリシー (DEP) を作成する必要があります。 この階層は、管理する 2 つのルート キーと、Microsoft によって自動生成および保護されている可用性キーを使用して、監査データを暗号化するためにサービスによって使用されます。

詳細な手順については、「 [顧客キーの設定](customer-key-set-up.md)」を参照してください。

セットアップが完了したら、作成したマルチワークロード DEP で識別されたキーを使用して、監査レコードを含む組織内のすべてのデータを暗号化Microsoft 365。

## <a name="offboarding-from-customer-key"></a>顧客キーからのオフボーディング

マルチワークロードの DEP の割り当てにカスタマー キーを使用しなくなった場合は、カスタマー キーから "オフボード" の要求を受けて Microsoft サポートに連絡する必要があります。 Microsoft Purview カスタマー キー チームに対してサービス要求を提出するようサポート チームに依頼します。 質問がある場合は、m365-ck@service.microsoft.com にお問い合 m365-ck@service.microsoft.com。 詳細については、「 [カスタマー キーから Microsoft マネージド キーへのロールバック](customer-key-manage.md#roll-back-from-customer-key-to-microsoft-managed-keys) 」を参照してください。

お客様は自分のキーを管理することを望めなくなり、CMK からオフボードを選択できます。
監査の場合- MMK にオンボードされていません。 そのため、テナントが CMK からオフボードになると、第 2 レベルの暗号化へのフォールバックは行われません。 データは、既定の Azure ストレージ暗号化によって保存時に暗号化されます。

<!--
Steps: 

- Customer reaches out to MDEPS team to offboard from CMK.

- MDEPS team offboards the customer and marks their DEPs as disabled -

- New data for the customer / tenant will not be encrypted

- Existing / Older encrypted data will be decrypted using the keys associated with the DEP

NOTE: Even after offboarding, tenant is expected to keep their pre-used encryption keys and keep the MDEPS AAD app access to the AKVs till the lifetime of their encrypted data.
-->

## <a name="offboarding-from-microsoft-365"></a>Microsoft 365からのオフボード

Microsoft Purview カスタマー キーでは、マルチワークロード DEP の削除はサポートされていません。 マルチワークロード DEP は、すべてのテナント ユーザー間で複数のワークロード間でデータを暗号化するために使用されます。 マルチワークロード DEP を削除すると、複数のワークロード間のデータにアクセスできなくなります。 Microsoft Purview サービスを完全に終了することにした場合は、 [文書化されたプロセス](/azure/active-directory/enterprise-users/directory-delete-howto)ごとにテナントの削除のパスを追跡できます。 Azure Active Directoryでテナントを削除する方法をご覧ください。

<!--
- Customer in this case wants to leave the M365 eco-system and ensure all their data is purged / deleted.
- In case of "multi-workload" DEP - purging or deleting the DEP is NOT allowed by policy.
- In this case the customer would revoke access to the AKV containing the CMK keys.
The customer would proceed with the Tenant Deprovisioning process in order to fully leave the service. They may revoke keys, but not required by the process.
- This change would be reflected in ~24 hours across ALE and MDEPS after caches have expired.
- Ideally since customer is exiting the eco-system, no more audit events would be generated for the customer. However in case there are new audit events for the customer, then they will NOT be encrypted using CMK as customer has offboarded / revoked key access.
-->

## <a name="more-information"></a>詳細情報

- 組織の監査レコードを暗号化するための実装手順を完了すると、最大で 24 時間かかります。
- 組織で他のワークロード (ExchangeやSharePointなど) に対する MDEPS サポートが既にある場合は、複数のワークロードに対してのみ有効にする必要があります。
- 監査用の顧客キーが実装された後に生成された監査レコード (または組織が複数のワークロードに対してカスタマー キーを実装した場合) のみが暗号化されます。 既存の監査レコードは暗号化されません。
