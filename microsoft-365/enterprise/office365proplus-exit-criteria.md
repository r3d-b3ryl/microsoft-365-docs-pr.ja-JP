---
title: Office 365 ProPlus の展開の終了条件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 構成が、Office 365 ProPlus インフラストラクチャの Microsoft 365 Enterprise の終了条件を満たしていることを確認します。
ms.openlocfilehash: c38539d85e1c826667b7a8a177a15ab75350aa5f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868986"
---
# <a name="office-365-proplus-deployment-exit-criteria"></a><span data-ttu-id="0c91d-103">Office 365 ProPlus の展開の終了条件</span><span class="sxs-lookup"><span data-stu-id="0c91d-103">Office 365 ProPlus deployment exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)

<span data-ttu-id="0c91d-104">*これは Microsoft 365 Enterprise および Microsoft 365 Education のバージョン E3 および E5 に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="0c91d-104">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="0c91d-105">展開プロセスの次のフェーズに移行する前に、構成が Office 365 ProPlus インフラストラクチャの次の必須条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c91d-105">Before you move on to the next phase in the deployment process, ensure that your configuration meets the following required criteria for Office 365 ProPlus infrastructure.</span></span>

- <span data-ttu-id="0c91d-106">インフラストラクチャと環境の評価が完了している。これには次のものが含まれる。</span><span class="sxs-lookup"><span data-stu-id="0c91d-106">Assessment of infrastructure and environment is complete, including:</span></span>

    - <span data-ttu-id="0c91d-107">クライアント デバイスの詳細</span><span class="sxs-lookup"><span data-stu-id="0c91d-107">Client device details</span></span>
    - <span data-ttu-id="0c91d-108">展開ツール</span><span class="sxs-lookup"><span data-stu-id="0c91d-108">Deployment tools</span></span>
    - <span data-ttu-id="0c91d-109">Office 365 のライセンスとアカウント</span><span class="sxs-lookup"><span data-stu-id="0c91d-109">Office 365 licensing and accounts</span></span>
    - <span data-ttu-id="0c91d-110">ネットワーク容量</span><span class="sxs-lookup"><span data-stu-id="0c91d-110">Network capability</span></span>
    - <span data-ttu-id="0c91d-111">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="0c91d-111">Application compatibility</span></span>

- <span data-ttu-id="0c91d-112">展開計画が完了している。これには次のものが含まれる。</span><span class="sxs-lookup"><span data-stu-id="0c91d-112">Deployment plan is complete, including:</span></span>

    - <span data-ttu-id="0c91d-113">Office 365 ProPlus の展開方法</span><span class="sxs-lookup"><span data-stu-id="0c91d-113">How to deploy Office 365 ProPlus</span></span>
    - <span data-ttu-id="0c91d-114">Office 365 ProPlus の更新の管理方法</span><span class="sxs-lookup"><span data-stu-id="0c91d-114">How to manage updates to Office 365 ProPlus</span></span>
    - <span data-ttu-id="0c91d-115">ネットワーク上のローカル ソースとクラウドのいずれから展開およびインストールを実行するか</span><span class="sxs-lookup"><span data-stu-id="0c91d-115">Whether to deploy and install from a local source on your network or from the cloud</span></span>
    - <span data-ttu-id="0c91d-116">どのクライアント デバイスにどの更新チャネルを割り当てるか</span><span class="sxs-lookup"><span data-stu-id="0c91d-116">Which client devices get which update channels</span></span>
    - <span data-ttu-id="0c91d-117">インストール パッケージが定義されている</span><span class="sxs-lookup"><span data-stu-id="0c91d-117">Installation packages defined</span></span>
    - <span data-ttu-id="0c91d-118">展開グループにすべてのクライアント デバイスが割り当てられている</span><span class="sxs-lookup"><span data-stu-id="0c91d-118">All client devices assigned to deployment groups</span></span>
    - <span data-ttu-id="0c91d-119">どの Office アプリケーション、アーキテクチャ、言語がどのクライアント デバイスにインストールされるか</span><span class="sxs-lookup"><span data-stu-id="0c91d-119">Which Office applications, architectures, and languages go to which client devices</span></span>

- <span data-ttu-id="0c91d-120">Office 365 ProPlus の展開が完了している。これには次のものが含まれる。</span><span class="sxs-lookup"><span data-stu-id="0c91d-120">Deployment of Office 365 ProPlus is complete, including:</span></span>

    - <span data-ttu-id="0c91d-121">すべてのクライアント デバイスに Office 365 ProPlus がインストールされている</span><span class="sxs-lookup"><span data-stu-id="0c91d-121">All client devices have Office 365 ProPlus installed</span></span>
    - <span data-ttu-id="0c91d-122">すべてのクライアント デバイスが適切な更新チャネルにあり、更新プログラムを受信している</span><span class="sxs-lookup"><span data-stu-id="0c91d-122">All client devices are in the appropriate update channel and are receiving updates</span></span>
    - <span data-ttu-id="0c91d-123">すべてのクライアント デバイスに適切な言語がインストールされているか、適切な言語が使用可能である</span><span class="sxs-lookup"><span data-stu-id="0c91d-123">All client devices have the appropriate languages installed or available</span></span>

## <a name="next-phase"></a><span data-ttu-id="0c91d-124">次のフェーズ</span><span class="sxs-lookup"><span data-stu-id="0c91d-124">Next phase</span></span> 


|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)| <span data-ttu-id="0c91d-125">Microsoft 365 Enterprise のエンドツーエンド展開プロセスの次のフェーズは、[モバイル デバイス管理](mobility-infrastructure.md)です。</span><span class="sxs-lookup"><span data-stu-id="0c91d-125">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [mobile device management](mobility-infrastructure.md).</span></span> |
