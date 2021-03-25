---
title: Microsoft Defender ATP for Mac を使用して望ましくない可能性のあるアプリケーションを検出およびブロックする
description: Microsoft Defender ATP for Mac を使用して、望ましくない可能性があるアプリケーション (PUA) を検出してブロックします。
keywords: microsoft、Defender、atp、mac、pua、pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6e65e847403160d24eac04a553ca16a46314e33d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187423"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="3ce9a-104">Microsoft Defender for Endpoint for Mac で望ましくない可能性のあるアプリケーションを検出してブロックする</span><span class="sxs-lookup"><span data-stu-id="3ce9a-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ce9a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3ce9a-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ce9a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3ce9a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3ce9a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ce9a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3ce9a-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="3ce9a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ce9a-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="3ce9a-110">Microsoft Defender for Endpoint for Mac の望ましくない可能性のあるアプリケーション (PUA) 保護機能は、ネットワーク内のエンドポイント上の PUA ファイルを検出してブロックできます。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint for Mac can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="3ce9a-111">これらのアプリケーションは、ウイルス、マルウェア、その他の種類の脅威とは見なされませんが、パフォーマンスや使用に悪影響を及ぼすエンドポイントに対してアクションを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="3ce9a-112">PUA は、評判が悪いと見なされるアプリケーションも参照できます。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="3ce9a-113">これらのアプリケーションは、ネットワークがマルウェアに感染するリスクを高め、マルウェアの感染を特定しにくくし、アプリケーションのクリーンアップで IT リソースを無駄にする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="3ce9a-114">メカニズム</span><span class="sxs-lookup"><span data-stu-id="3ce9a-114">How it works</span></span>

<span data-ttu-id="3ce9a-115">Microsoft Defender for Endpoint for Mac では、PUA ファイルを検出して報告できます。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-115">Microsoft Defender for Endpoint for Mac can detect and report PUA files.</span></span> <span data-ttu-id="3ce9a-116">ブロック モードで構成すると、PUA ファイルは検疫に移動されます。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="3ce9a-117">エンドポイントで PUA が検出されると、Microsoft Defender for Endpoint for Mac は、通知が無効にされていない限り、ユーザーに通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint for Mac presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="3ce9a-118">脅威名には"Application" という単語が含まれる。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="3ce9a-119">PUA 保護の構成</span><span class="sxs-lookup"><span data-stu-id="3ce9a-119">Configure PUA protection</span></span>

<span data-ttu-id="3ce9a-120">Microsoft Defender for Endpoint for Mac の PUA 保護は、次のいずれかの方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-120">PUA protection in Microsoft Defender for Endpoint for Mac can be configured in one of the following ways:</span></span>

- <span data-ttu-id="3ce9a-121">**Off**: PUA 保護は無効です。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="3ce9a-122">**監査**: PUA ファイルは製品ログに報告されますが、Microsoft Defender セキュリティ センターでは報告されません。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="3ce9a-123">ユーザーに通知は表示されません。また、製品によるアクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="3ce9a-124">**ブロック**: PUA ファイルは、製品ログと Microsoft Defender セキュリティ センターで報告されます。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="3ce9a-125">ユーザーに通知が表示され、製品によってアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="3ce9a-126">既定では、監査モードで PUA 保護 **が構成** されています。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="3ce9a-127">PUA ファイルの処理方法は、コマンド ラインまたは管理コンソールから構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="3ce9a-128">コマンド ライン ツールを使用して PUA 保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="3ce9a-129">ターミナルで、次のコマンドを実行して PUA 保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="3ce9a-130">管理コンソールを使用して PUA 保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="3ce9a-131">企業では、他の製品設定の構成方法と同様に、JAMF や Intune などの管理コンソールから PUA 保護を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="3ce9a-132">詳細については、「Microsoft Defender [](mac-preferences.md#threat-type-settings) for Endpoint for Mac の設定」の「脅威の種類の設定[」セクションを参照](mac-preferences.md)してください。</span><span class="sxs-lookup"><span data-stu-id="3ce9a-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3ce9a-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ce9a-133">Related topics</span></span>

- [<span data-ttu-id="3ce9a-134">Microsoft Defender for Endpoint for Mac の基本設定を設定する</span><span class="sxs-lookup"><span data-stu-id="3ce9a-134">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>](mac-preferences.md)