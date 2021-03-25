---
title: 適切な設定で高度な狩猟範囲を拡張する
description: 高度な検索で最も包括的なデータを取得するために、Windows デバイスや他の設定の監査設定を確認する
keywords: 高度なハンティング、インシデント、ピボット、エンティティ、監査設定、ユーザー アカウント管理、セキュリティ グループ管理、脅威狩猟、検索、クエリ、テレメトリ、mdatp、Microsoft Defender ATP、Microsoft Defender for Endpoint、Windows Defender、Windows Defender ATP、Windows Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: 60e8710415e328d06fac4c02e428094e5e4bcc92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067460"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="cb707-104">適切な設定で高度な狩猟範囲を拡張する</span><span class="sxs-lookup"><span data-stu-id="cb707-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cb707-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cb707-105">**Applies to:**</span></span>
- [<span data-ttu-id="cb707-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cb707-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="cb707-107">[高度な検索は](advanced-hunting-overview.md) 、組織全体からのデータに依存します。</span><span class="sxs-lookup"><span data-stu-id="cb707-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from across your organization.</span></span> <span data-ttu-id="cb707-108">可能な限り包括的なデータを取得するには、対応するデータ ソースに正しい設定が含されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb707-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="cb707-109">Windows デバイスでの高度なセキュリティ監査</span><span class="sxs-lookup"><span data-stu-id="cb707-109">Advanced security auditing on Windows devices</span></span>

<span data-ttu-id="cb707-110">これらの高度な監査設定をオンにし、ローカル アカウント管理、ローカル セキュリティ グループ管理、サービスの作成など、デバイス上のアクティビティに関するデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="cb707-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

<span data-ttu-id="cb707-111">データ</span><span class="sxs-lookup"><span data-stu-id="cb707-111">Data</span></span> | <span data-ttu-id="cb707-112">説明</span><span class="sxs-lookup"><span data-stu-id="cb707-112">Description</span></span> | <span data-ttu-id="cb707-113">スキーマ テーブル</span><span class="sxs-lookup"><span data-stu-id="cb707-113">Schema table</span></span> | <span data-ttu-id="cb707-114">構成する方法</span><span class="sxs-lookup"><span data-stu-id="cb707-114">How to configure</span></span>
-|-|-|-
<span data-ttu-id="cb707-115">アカウント管理</span><span class="sxs-lookup"><span data-stu-id="cb707-115">Account management</span></span> | <span data-ttu-id="cb707-116">ローカル アカウントの作成、削除、その他のアカウント関連のアクティビティを示すさまざまな値 `ActionType` としてキャプチャされるイベント</span><span class="sxs-lookup"><span data-stu-id="cb707-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="cb707-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="cb707-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="cb707-118">- 高度なセキュリティ監査ポリシーの展開: [ユーザー アカウント管理の監査](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="cb707-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="cb707-119">- [高度なセキュリティ監査ポリシーの詳細](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="cb707-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="cb707-120">セキュリティ グループの管理</span><span class="sxs-lookup"><span data-stu-id="cb707-120">Security group management</span></span> | <span data-ttu-id="cb707-121">ローカル セキュリティ グループの作成および他のローカル グループ管理アクティビティを示すさまざまな `ActionType` 値としてキャプチャされたイベント</span><span class="sxs-lookup"><span data-stu-id="cb707-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="cb707-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="cb707-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="cb707-123">- 高度なセキュリティ監査ポリシーの展開: [セキュリティ グループ管理の監査](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="cb707-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="cb707-124">- [高度なセキュリティ監査ポリシーの詳細](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="cb707-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="cb707-125">サービスのインストール</span><span class="sxs-lookup"><span data-stu-id="cb707-125">Service installation</span></span> | <span data-ttu-id="cb707-126">サービスが作成されたことを示 `ActionType` す値 `ServiceInstalled` でキャプチャされたイベント</span><span class="sxs-lookup"><span data-stu-id="cb707-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="cb707-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="cb707-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="cb707-128">- 高度なセキュリティ監査ポリシーの展開: [セキュリティ システム拡張機能の監査](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="cb707-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="cb707-129">- [高度なセキュリティ監査ポリシーの詳細](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="cb707-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>

## <a name="related-topics"></a><span data-ttu-id="cb707-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb707-130">Related topics</span></span>

- [<span data-ttu-id="cb707-131">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="cb707-131">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cb707-132">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="cb707-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cb707-133">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="cb707-133">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="cb707-134">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="cb707-134">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="cb707-135">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="cb707-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="cb707-136">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="cb707-136">Custom detections overview</span></span>](overview-custom-detections.md)