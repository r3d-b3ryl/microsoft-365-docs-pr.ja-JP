---
title: Microsoft の脅威保護での自動調査および応答機能の修復処置
description: Microsoft Threat Protection での自動調査および対応機能の概要を説明します
keywords: 自動化、調査、警告、トリガー、アクション、修復
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175943"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="a9153-104">Microsoft の脅威保護での自動調査および応答機能の修復処置</span><span class="sxs-lookup"><span data-stu-id="a9153-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="a9153-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a9153-105">**Applies to:**</span></span>
- <span data-ttu-id="a9153-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a9153-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a9153-107">Microsoft の脅威保護の自動化された調査と応答機能には、特定の修復アクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9153-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="a9153-108">一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="a9153-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="a9153-109">その他の修復アクションは、電子メールコンテンツに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="a9153-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="a9153-110">次の表に、Microsoft の脅威保護で現在サポートされている修復アクションの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a9153-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="a9153-111">エンドポイントの修復アクション</span><span class="sxs-lookup"><span data-stu-id="a9153-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="a9153-112">メールの修復アクション</span><span class="sxs-lookup"><span data-stu-id="a9153-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="a9153-113">ファイルの検疫</span><span class="sxs-lookup"><span data-stu-id="a9153-113">Quarantine file</span></span><br/><span data-ttu-id="a9153-114">レジストリ キーの削除</span><span class="sxs-lookup"><span data-stu-id="a9153-114">Remove registry key</span></span><br/><span data-ttu-id="a9153-115">プロセスの強制終了</span><span class="sxs-lookup"><span data-stu-id="a9153-115">Kill process</span></span> <br/><span data-ttu-id="a9153-116">サービスの停止</span><span class="sxs-lookup"><span data-stu-id="a9153-116">Stop service</span></span> <br/><span data-ttu-id="a9153-117">レジストリ キーの削除</span><span class="sxs-lookup"><span data-stu-id="a9153-117">Remove registry key</span></span> <br/><span data-ttu-id="a9153-118">ドライバーの無効化</span><span class="sxs-lookup"><span data-stu-id="a9153-118">Disable driver</span></span> <br/><span data-ttu-id="a9153-119">スケジュールされたタスクの実行</span><span class="sxs-lookup"><span data-stu-id="a9153-119">Remove scheduled task</span></span>      |<span data-ttu-id="a9153-120">メール メッセージまたはクラスターの論理的な削除</span><span class="sxs-lookup"><span data-stu-id="a9153-120">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="a9153-121">URL のブロック (クリック時)</span><span class="sxs-lookup"><span data-stu-id="a9153-121">Block URL (time-of-click)</span></span><br/><span data-ttu-id="a9153-122">外部メール転送の無効化</span><span class="sxs-lookup"><span data-stu-id="a9153-122">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="a9153-123">修復が保留になっているか、既に完了しているかにかかわらず、[アクションセンター](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="a9153-123">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a9153-124">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a9153-124">Next steps</span></span>

- [<span data-ttu-id="a9153-125">自動調査と対応に関連するアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="a9153-125">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="a9153-126">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="a9153-126">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
