---
title: 適切な設定で高度な狩猟範囲を拡張する
description: 高度な検索で最も包括的なデータを取得するために、Windows デバイスや他の設定の監査設定を確認する
keywords: 高度なハンティング、インシデント、ピボット、エンティティ、監査設定、ユーザー アカウント管理、セキュリティ グループ管理、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、Microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: eaa0068fe52119bfd9dc2381b253b259cb8df907
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062084"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="4225c-104">適切な設定で高度な狩猟範囲を拡張する</span><span class="sxs-lookup"><span data-stu-id="4225c-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4225c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4225c-105">**Applies to:**</span></span>
- <span data-ttu-id="4225c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4225c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4225c-107">[高度な検索](advanced-hunting-overview.md) は、デバイス、Office 365 ワークスペース、Azure AD、Microsoft Defender for Identity など、さまざまなソースからのデータに依存します。</span><span class="sxs-lookup"><span data-stu-id="4225c-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from various sources, including your devices, your Office 365 workspaces, Azure AD, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="4225c-108">可能な限り包括的なデータを取得するには、対応するデータ ソースに正しい設定が含されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4225c-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="4225c-109">Windows デバイスでの高度なセキュリティ監査</span><span class="sxs-lookup"><span data-stu-id="4225c-109">Advanced security auditing on Windows devices</span></span>
<span data-ttu-id="4225c-110">これらの高度な監査設定をオンにし、ローカル アカウント管理、ローカル セキュリティ グループ管理、サービスの作成など、デバイス上のアクティビティに関するデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="4225c-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

| <span data-ttu-id="4225c-111">データ</span><span class="sxs-lookup"><span data-stu-id="4225c-111">Data</span></span> | <span data-ttu-id="4225c-112">説明</span><span class="sxs-lookup"><span data-stu-id="4225c-112">Description</span></span> | <span data-ttu-id="4225c-113">スキーマ テーブル</span><span class="sxs-lookup"><span data-stu-id="4225c-113">Schema table</span></span> | <span data-ttu-id="4225c-114">構成する方法</span><span class="sxs-lookup"><span data-stu-id="4225c-114">How to configure</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="4225c-115">アカウント管理</span><span class="sxs-lookup"><span data-stu-id="4225c-115">Account management</span></span> | <span data-ttu-id="4225c-116">ローカル アカウントの作成、削除、その他のアカウント関連のアクティビティを示すさまざまな値 `ActionType` としてキャプチャされるイベント</span><span class="sxs-lookup"><span data-stu-id="4225c-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="4225c-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="4225c-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="4225c-118">- 高度なセキュリティ監査ポリシーの展開: [ユーザー アカウント管理の監査](/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="4225c-118">- Deploy an advanced security audit policy: [Audit User Account Management](/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="4225c-119">- [高度なセキュリティ監査ポリシーの詳細](/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="4225c-119">- [Learn about advanced security audit policies](/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |
| <span data-ttu-id="4225c-120">セキュリティ グループの管理</span><span class="sxs-lookup"><span data-stu-id="4225c-120">Security group management</span></span> | <span data-ttu-id="4225c-121">ローカル セキュリティ グループの作成および他のローカル グループ管理アクティビティを示すさまざまな `ActionType` 値としてキャプチャされたイベント</span><span class="sxs-lookup"><span data-stu-id="4225c-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="4225c-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="4225c-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="4225c-123">- 高度なセキュリティ監査ポリシーの展開: [セキュリティ グループ管理の監査](/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="4225c-123">- Deploy an advanced security audit policy: [Audit Security Group Management](/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="4225c-124">- [高度なセキュリティ監査ポリシーの詳細](/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="4225c-124">- [Learn about advanced security audit policies](/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |
| <span data-ttu-id="4225c-125">サービスのインストール</span><span class="sxs-lookup"><span data-stu-id="4225c-125">Service installation</span></span> | <span data-ttu-id="4225c-126">サービスが作成されたことを示 `ActionType` す値 `ServiceInstalled` でキャプチャされたイベント</span><span class="sxs-lookup"><span data-stu-id="4225c-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="4225c-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="4225c-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="4225c-128">- 高度なセキュリティ監査ポリシーの展開: [セキュリティ システム拡張機能の監査](/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="4225c-128">- Deploy an advanced security audit policy: [Audit Security System Extension](/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="4225c-129">- [高度なセキュリティ監査ポリシーの詳細](/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="4225c-129">- [Learn about advanced security audit policies](/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span> |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a><span data-ttu-id="4225c-130">ドメイン コントローラー上の Id センサー用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4225c-130">Microsoft Defender for Identity sensor on the domain controller</span></span>
<span data-ttu-id="4225c-131">オンプレミスで Active Directory を実行している場合は、Microsoft Defender for Identity のデータを取得するには、ドメイン コントローラーに Microsoft Defender for Identity センサーをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4225c-131">If you're running Active Directory on premises, you need to install the Microsoft Defender for Identity sensor on the domain controller to get data for Microsoft Defender for Identity.</span></span> <span data-ttu-id="4225c-132">インストールされ、適切に構成されている場合、このデータは、Microsoft Defender for Identity を介した高度な検索にもフィードされ、ネットワーク内の ID 情報とイベントの全体像を提供します。</span><span class="sxs-lookup"><span data-stu-id="4225c-132">When installed and properly configured, this data also feeds into advanced hunting through Microsoft Defender for Identity and provides a more holistic picture of identity information and events in your network.</span></span> <span data-ttu-id="4225c-133">また、このデータを使用すると、Microsoft Defender for Identity が高度な狩猟の対象となる関連するアラートを生成する機能も強化されます。</span><span class="sxs-lookup"><span data-stu-id="4225c-133">This data also enhances the ability of Microsoft Defender for Identity to generate relevant alerts that are also covered by advanced hunting.</span></span> 

| <span data-ttu-id="4225c-134">データ</span><span class="sxs-lookup"><span data-stu-id="4225c-134">Data</span></span> | <span data-ttu-id="4225c-135">説明</span><span class="sxs-lookup"><span data-stu-id="4225c-135">Description</span></span> | <span data-ttu-id="4225c-136">スキーマ テーブル</span><span class="sxs-lookup"><span data-stu-id="4225c-136">Schema table</span></span> | <span data-ttu-id="4225c-137">構成する方法</span><span class="sxs-lookup"><span data-stu-id="4225c-137">How to configure</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="4225c-138">ドメイン コントローラ</span><span class="sxs-lookup"><span data-stu-id="4225c-138">Domain controller</span></span> | <span data-ttu-id="4225c-139">Microsoft Defender for Identity に送信されるオンプレミスの Active Directory からのデータ、アカウントの詳細、ログオン アクティビティ、Active Directory クエリなどの ID 関連情報の強化</span><span class="sxs-lookup"><span data-stu-id="4225c-139">Data from on-premises Active Directory sent to Microsoft Defender for Identity, enriching identity-related information, such as account details, logon activity, and Active Directory queries</span></span> | <span data-ttu-id="4225c-140">[IdentityInfo、IdentityLogonEvents、IdentityQueryEvents](advanced-hunting-identitylogonevents-table.md)などの複数の[](advanced-hunting-identityinfo-table.md)[テーブル](advanced-hunting-identityqueryevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="4225c-140">Multiple tables, including [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), and [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)</span></span>  | <span data-ttu-id="4225c-141">- [Microsoft Defender for Identity センサーのインストール](/azure-advanced-threat-protection/install-atp-step4)</span><span class="sxs-lookup"><span data-stu-id="4225c-141">- [Install the Microsoft Defender for Identity sensor](/azure-advanced-threat-protection/install-atp-step4)</span></span><br><span data-ttu-id="4225c-142">- [関連する Windows イベントを有効にする](/azure-advanced-threat-protection/configure-event-collection)</span><span class="sxs-lookup"><span data-stu-id="4225c-142">- [Turn on relevant Windows Events](/azure-advanced-threat-protection/configure-event-collection)</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4225c-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="4225c-143">Related topics</span></span>
- [<span data-ttu-id="4225c-144">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="4225c-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4225c-145">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="4225c-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)