---
title: Microsoft Defender ATP for Linux を使用して望ましくない可能性のあるアプリケーションを検出およびブロックする
description: Microsoft Defender ATP for Linux を使用して、望ましくない可能性があるアプリケーション (PUA) を検出してブロックします。
keywords: microsoft、Defender、atp、Linux、pua、pus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e7ac620896bad9adb73308223e28976e219d36d0
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687867"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c7fef-104">Linux 上のエンドポイント用 Microsoft Defender を使用して、望ましくない可能性のあるアプリケーションを検出およびブロックする</span><span class="sxs-lookup"><span data-stu-id="c7fef-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c7fef-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c7fef-105">**Applies to:**</span></span>
- [<span data-ttu-id="c7fef-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c7fef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c7fef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7fef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c7fef-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="c7fef-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c7fef-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c7fef-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="c7fef-110">Defender for Endpoint for Linux の望ましくない可能性のあるアプリケーション (PUA) 保護機能は、ネットワーク内のエンドポイント上の PUA ファイルを検出してブロックできます。</span><span class="sxs-lookup"><span data-stu-id="c7fef-110">The potentially unwanted application (PUA) protection feature in Defender for Endpoint for Linux can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="c7fef-111">これらのアプリケーションは、ウイルス、マルウェア、その他の種類の脅威とは見なされませんが、パフォーマンスや使用に悪影響を及ぼすエンドポイントに対してアクションを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7fef-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="c7fef-112">PUA は、評判が悪いと見なされるアプリケーションも参照できます。</span><span class="sxs-lookup"><span data-stu-id="c7fef-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="c7fef-113">これらのアプリケーションは、ネットワークがマルウェアに感染するリスクを高め、マルウェアの感染を特定しにくくし、アプリケーションのクリーンアップで IT リソースを無駄にする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7fef-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="c7fef-114">メカニズム</span><span class="sxs-lookup"><span data-stu-id="c7fef-114">How it works</span></span>

<span data-ttu-id="c7fef-115">Defender for Endpoint for Linux では、PUA ファイルを検出して報告できます。</span><span class="sxs-lookup"><span data-stu-id="c7fef-115">Defender for Endpoint for Linux can detect and report PUA files.</span></span> <span data-ttu-id="c7fef-116">ブロック モードで構成すると、PUA ファイルは検疫に移動されます。</span><span class="sxs-lookup"><span data-stu-id="c7fef-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="c7fef-117">エンドポイントで PUA が検出されると、Defender for Endpoint for Linux は脅威履歴に感染の記録を保持します。</span><span class="sxs-lookup"><span data-stu-id="c7fef-117">When a PUA is detected on an endpoint, Defender for Endpoint for Linux keeps a record of the infection in the threat history.</span></span> <span data-ttu-id="c7fef-118">履歴は、Microsoft Defender セキュリティ センター ポータルまたはコマンド ライン ツール `mdatp` を使用して視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="c7fef-118">The history can be visualized from the Microsoft Defender Security Center portal or through the `mdatp` command-line tool.</span></span> <span data-ttu-id="c7fef-119">脅威名には"Application" という単語が含まれる。</span><span class="sxs-lookup"><span data-stu-id="c7fef-119">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="c7fef-120">PUA 保護の構成</span><span class="sxs-lookup"><span data-stu-id="c7fef-120">Configure PUA protection</span></span>

<span data-ttu-id="c7fef-121">Defender for Endpoint for Linux の PUA 保護は、次のいずれかの方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="c7fef-121">PUA protection in Defender for Endpoint for Linux can be configured in one of the following ways:</span></span>

- <span data-ttu-id="c7fef-122">**Off**: PUA 保護は無効です。</span><span class="sxs-lookup"><span data-stu-id="c7fef-122">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="c7fef-123">**監査**: PUA ファイルは製品ログに報告されますが、Microsoft Defender セキュリティ センターでは報告されません。</span><span class="sxs-lookup"><span data-stu-id="c7fef-123">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="c7fef-124">感染の記録は脅威の履歴に保存され、製品によるアクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c7fef-124">No record of the infection is stored in the threat history and no action is taken by the product.</span></span>
- <span data-ttu-id="c7fef-125">**ブロック**: PUA ファイルは、製品ログと Microsoft Defender セキュリティ センターで報告されます。</span><span class="sxs-lookup"><span data-stu-id="c7fef-125">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="c7fef-126">感染の記録は脅威の履歴に保存され、製品によってアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c7fef-126">A record of the infection is stored in the threat history and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="c7fef-127">既定では、監査モードで PUA 保護 **が構成** されています。</span><span class="sxs-lookup"><span data-stu-id="c7fef-127">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="c7fef-128">PUA ファイルの処理方法は、コマンド ラインまたは管理コンソールから構成できます。</span><span class="sxs-lookup"><span data-stu-id="c7fef-128">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="c7fef-129">コマンド ライン ツールを使用して PUA 保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="c7fef-129">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="c7fef-130">ターミナルで、次のコマンドを実行して PUA 保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="c7fef-130">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="c7fef-131">管理コンソールを使用して PUA 保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="c7fef-131">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="c7fef-132">企業では、他の製品設定の構成方法と同様に、Puppet や Ansible などの管理コンソールから PUA 保護を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c7fef-132">In your enterprise, you can configure PUA protection from a management console, such as Puppet or Ansible, similarly to how other product settings are configured.</span></span> <span data-ttu-id="c7fef-133">詳細については、「Defender for [](linux-preferences.md#threat-type-settings) Endpoint for Linux の設定」の「脅威の種類の設定[」セクションを参照](linux-preferences.md)してください。</span><span class="sxs-lookup"><span data-stu-id="c7fef-133">For more information, see the [Threat type settings](linux-preferences.md#threat-type-settings) section of the [Set preferences for Defender for Endpoint for Linux](linux-preferences.md) article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c7fef-134">関連記事</span><span class="sxs-lookup"><span data-stu-id="c7fef-134">Related articles</span></span>

- [<span data-ttu-id="c7fef-135">Defender for Endpoint for Linux の基本設定を設定する</span><span class="sxs-lookup"><span data-stu-id="c7fef-135">Set preferences for Defender for Endpoint for Linux</span></span>](linux-preferences.md)
