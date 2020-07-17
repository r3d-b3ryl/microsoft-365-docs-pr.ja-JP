---
title: Microsoft Threat Protection サービスに関する問題のトラブルシューティング
description: 既知の Microsoft Threat Protection の問題の解決策と対処方法を見つける
keywords: Microsoft の脅威保護、トラブルシューティング、Azure ATP、問題、アドオン、設定ページのトラブルシューティング
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e19e5758f4d42799c96ecec51fd6295e3da19f9b
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844920"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="0f37a-104">Microsoft Threat Protection サービスに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0f37a-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="0f37a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0f37a-105">**Applies to:**</span></span>
- <span data-ttu-id="0f37a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0f37a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0f37a-107">このセクションでは、Microsoft Threat Protection サービスを使用するときに発生する可能性のある問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="0f37a-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="0f37a-108">Microsoft Threat Protection コンテンツが表示されない</span><span class="sxs-lookup"><span data-stu-id="0f37a-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="0f37a-109">ポータルでインシデント、アクションセンター、探している機能など、ナビゲーションウィンドウに機能が表示されない場合は、テナントに適切なライセンスがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f37a-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="0f37a-110">詳細については、「[前提条件](prerequisites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f37a-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="0f37a-111">Microsoft Threat Protection インシデントに Azure ATP アラートが表示されない</span><span class="sxs-lookup"><span data-stu-id="0f37a-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="0f37a-112">環境に Azure ATP が展開されていても、Microsoft Threat Protection インシデントの一部として Azure ATP アラートが表示されない場合は、Microsoft Cloud App Security および Azure ATP 統合が有効であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f37a-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="0f37a-113">詳細については、「[Azure ATP 統合](https://docs.microsoft.com/cloud-app-security/aatp-integration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f37a-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="0f37a-114">サービスをオンにするための設定ページはどこにありますか。</span><span class="sxs-lookup"><span data-stu-id="0f37a-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="0f37a-115">Microsoft の脅威保護を有効にするには、Microsoft 365 セキュリティセンターのナビゲーションウィンドウの**設定**にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0f37a-115">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="0f37a-116">このナビゲーション項目は、[必要なアクセス許可とライセンス](mtp-enable.md#check-license-eligibility-and-required-permissions)がある場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f37a-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

