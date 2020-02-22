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
ms.openlocfilehash: 65ace4bda091b3e000d25a984b706f26fe9c8696
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225485"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="d58e1-104">Microsoft の脅威保護での自動調査および応答機能の修復処置</span><span class="sxs-lookup"><span data-stu-id="d58e1-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="d58e1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d58e1-105">**Applies to:**</span></span>
- <span data-ttu-id="d58e1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d58e1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d58e1-107">Microsoft の脅威保護の自動化された調査と応答機能には、特定の修復アクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d58e1-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="d58e1-108">一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d58e1-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="d58e1-109">その他の修復アクションは、電子メールコンテンツに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="d58e1-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="d58e1-110">次の表に、Microsoft の脅威保護で現在サポートされている修復アクションの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="d58e1-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="d58e1-111">エンドポイントの修復アクション</span><span class="sxs-lookup"><span data-stu-id="d58e1-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="d58e1-112">メールの修復アクション</span><span class="sxs-lookup"><span data-stu-id="d58e1-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="d58e1-113">ファイルの検疫</span><span class="sxs-lookup"><span data-stu-id="d58e1-113">Quarantine file</span></span><br/><span data-ttu-id="d58e1-114">レジストリ キーの削除</span><span class="sxs-lookup"><span data-stu-id="d58e1-114">Remove registry key</span></span><br/><span data-ttu-id="d58e1-115">プロセスの強制終了</span><span class="sxs-lookup"><span data-stu-id="d58e1-115">Kill process</span></span> <br/><span data-ttu-id="d58e1-116">サービスの停止</span><span class="sxs-lookup"><span data-stu-id="d58e1-116">Stop service</span></span> <br/><span data-ttu-id="d58e1-117">ドライバーの無効化</span><span class="sxs-lookup"><span data-stu-id="d58e1-117">Disable driver</span></span> <br/><span data-ttu-id="d58e1-118">スケジュールされたタスクの実行</span><span class="sxs-lookup"><span data-stu-id="d58e1-118">Remove scheduled task</span></span>      |<span data-ttu-id="d58e1-119">メール メッセージまたはクラスターの論理的な削除</span><span class="sxs-lookup"><span data-stu-id="d58e1-119">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="d58e1-120">URL のブロック (クリック時)</span><span class="sxs-lookup"><span data-stu-id="d58e1-120">Block URL (time-of-click)</span></span><br/><span data-ttu-id="d58e1-121">外部メール転送の無効化</span><span class="sxs-lookup"><span data-stu-id="d58e1-121">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="d58e1-122">修復が保留になっているか、既に完了しているかにかかわらず、[アクションセンター](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="d58e1-122">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d58e1-123">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d58e1-123">Next steps</span></span>

- [<span data-ttu-id="d58e1-124">自動調査と対応に関連するアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="d58e1-124">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="d58e1-125">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="d58e1-125">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
