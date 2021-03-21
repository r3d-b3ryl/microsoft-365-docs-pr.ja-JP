---
title: Exact Data Match アクティビティの通知を作成する (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Exact Data Match アクティビティの通知を作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e2f67ef0f276211483519bd5e246e4e041b2b15
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919363"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a>Exact Data Match アクティビティの通知を作成する (プレビュー)

[Exact Data Match (EDM) を使用してカスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)と、[監査ログ](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log)に作成されるアクティビティが多数あります。 [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell コマンドレットを使用して、次のアクティビティが発生したときに知らせる通知を作成できます。

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

> [!NOTE]
> EDM アクティビティの通知を作成できるのは、World Wide クラウドと GCC クラウドだけです。

## <a name="pre-requisites"></a>前提条件

使用するアカウントは、次のいずれかである必要があります。

- グローバル管理者
- コンプライアンス管理者
- Exchange Online 管理者

DLP アクセス許可の詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

これらのサブスクリプションには、EDM ベースの分類が含まれています

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 Compliance 
- Microsoft E5/A5 Information Protection and Governance

DLP ライセンスの詳細については、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)」を参照してください。

## <a name="configure-notifications-for-edm-activities"></a>EDM アクティビティの通知を構成する

1. [セキュリティ/コンプライアンス センターの PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps) に接続する 

2. 通知を作成するアクティビティを使用して、`New-ProtectionAlert` コマンドレットを実行します。  たとえば、**UploadDataCompleted** 操作が発生したときに通知を受け取りたい場合は、実行できる

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

**UploadDataFailed** に対して実行します

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a>関連記事

- [Exact Data Match (EDM) によりカスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps)