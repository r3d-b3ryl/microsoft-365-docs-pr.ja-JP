---
title: Microsoft Defender セキュリティ センターの設定を構成する
description: '[設定] ページを使用して、一般的な設定、アクセス許可、API、およびルールを構成します。'
keywords: 設定、一般的な設定、アクセス許可、API、ルール
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bb76b59860b761abceddfe07728c77e1734a0d73
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068476"
---
# <a name="configure-microsoft-defender-security-center-settings"></a><span data-ttu-id="1495b-104">Microsoft Defender セキュリティ センターの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="1495b-104">Configure Microsoft Defender Security Center settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1495b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1495b-105">**Applies to:**</span></span>
- [<span data-ttu-id="1495b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1495b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="1495b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1495b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="1495b-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="1495b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1495b-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="1495b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-prefsettings-abovefoldlink)

<span data-ttu-id="1495b-110">[設定 **] メニュー** を使用して、一般的な設定、高度な機能を変更し、プレビュー エクスペリエンス、電子メール通知、カスタム脅威インテリジェンス機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1495b-110">Use the **Settings** menu to modify general settings, advanced features, enable the preview experience, email notifications, and the custom threat intelligence feature.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1495b-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1495b-111">In this section</span></span>

<span data-ttu-id="1495b-112">トピック</span><span class="sxs-lookup"><span data-stu-id="1495b-112">Topic</span></span> | <span data-ttu-id="1495b-113">説明</span><span class="sxs-lookup"><span data-stu-id="1495b-113">Description</span></span>
:---|:---
<span data-ttu-id="1495b-114">全般設定</span><span class="sxs-lookup"><span data-stu-id="1495b-114">General settings</span></span> | <span data-ttu-id="1495b-115">オンボーディング プロセスの一部として以前に定義された一般的な設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="1495b-115">Modify your general settings that were previously defined as part of the onboarding process.</span></span>
<span data-ttu-id="1495b-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1495b-116">Permissions</span></span> | <span data-ttu-id="1495b-117">RBAC とデバイス グループを使用してポータル アクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="1495b-117">Manage portal access using RBAC as well as device groups.</span></span>
<span data-ttu-id="1495b-118">API</span><span class="sxs-lookup"><span data-stu-id="1495b-118">APIs</span></span> | <span data-ttu-id="1495b-119">脅威の Intel と SIEM の統合を有効にする。</span><span class="sxs-lookup"><span data-stu-id="1495b-119">Enable the threat intel and SIEM integration.</span></span>
<span data-ttu-id="1495b-120">ルール</span><span class="sxs-lookup"><span data-stu-id="1495b-120">Rules</span></span> | <span data-ttu-id="1495b-121">抑制ルールとオートメーション設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1495b-121">Configure suppressions rules and automation settings.</span></span>
<span data-ttu-id="1495b-122">デバイスの管理</span><span class="sxs-lookup"><span data-stu-id="1495b-122">Device management</span></span> | <span data-ttu-id="1495b-123">オンボードデバイスとオフボード デバイス。</span><span class="sxs-lookup"><span data-stu-id="1495b-123">Onboard and offboard devices.</span></span>
