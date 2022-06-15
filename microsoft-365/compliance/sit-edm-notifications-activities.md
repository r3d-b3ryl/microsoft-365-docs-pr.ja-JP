---
title: Exact Data Match アクティビティの通知を作成する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Exact Data Match アクティビティの通知を作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 75a0e3c50d9dc540bf76187e6aedcbd5642d250b
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66009390"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>Exact Data Match アクティビティの通知を作成する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

[Exact Data Match (EDM) を使用してカスタムの機密情報の種類を作成する](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)と、[監査ログ](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log)に作成されるアクティビティが多数あります。 [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell コマンドレットを使用して、次のアクティビティが発生したときに知らせる通知を作成できます。

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

> [!NOTE]
 EDM アクティビティの通知を作成できるのは、World Wide クラウドと GCC クラウドだけです。

## <a name="pre-requisites"></a>前提条件

使用するアカウントは、次のいずれかである必要があります。

- グローバル管理者
- コンプライアンス管理者
- Exchange Online 管理者

DLP アクセス許可の詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

これらのサブスクリプションには、EDM ベースの分類が含まれています。

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 Compliance 
- Microsoft E5/A5 Information Protection and Governance

DLP ライセンスの詳細については、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)」を参照してください。

## <a name="configure-notifications-for-edm-activities"></a>EDM アクティビティの通知を構成する

1. [セキュリティ/コンプライアンス PowerShell](/powershell/exchange/connect-to-scc-powershell) に接続します。

2. 通知を作成するアクティビティを使用して、`New-ProtectionAlert` コマンドレットを実行します。  たとえば、**UploadDataCompleted** 操作が発生したときに通知を受け取りたい場合は、以下を実行します。

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    **UploadDataFailed** に対して、次のコマンドを実行できます。
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a>関連記事

- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert)
