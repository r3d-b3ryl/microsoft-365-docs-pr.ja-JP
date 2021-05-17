---
title: ユーザーのプロトコル認識を有効Microsoft Defender ウイルス対策
description: デバイスのプロトコル認識を有効Microsoft Defender ウイルス対策。
keywords: Microsoft Defender ウイルス対策マルウェア対策、セキュリティ、防御側、プロトコル認識
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296479"
---
# <a name="turn-on-protocol-recognition"></a><span data-ttu-id="09f25-104">プロトコル認識を有効にする</span><span class="sxs-lookup"><span data-stu-id="09f25-104">Turn on protocol recognition</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09f25-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="09f25-105">**Applies to:**</span></span>

- [<span data-ttu-id="09f25-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="09f25-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="09f25-107">このポリシー設定を使用すると、既知の脆弱性の悪用に対するネットワーク保護のためのプロトコル認識を構成できます。</span><span class="sxs-lookup"><span data-stu-id="09f25-107">This policy setting allows you to configure protocol recognition for network protection against exploits of known vulnerabilities.</span></span> <span data-ttu-id="09f25-108">この設定を有効または無効にすると、プロトコル認識が有効になります。</span><span class="sxs-lookup"><span data-stu-id="09f25-108">If you enable or do not configure this setting, protocol recognition will be enabled.</span></span> <span data-ttu-id="09f25-109">この設定を無効にすると、プロトコル認識は無効になります。</span><span class="sxs-lookup"><span data-stu-id="09f25-109">If you disable this setting, protocol recognition will be disabled.</span></span>

## <a name="use-group-policy-to-configure-protocol-recognition"></a><span data-ttu-id="09f25-110">グループ ポリシーを使用してプロトコル認識を構成する</span><span class="sxs-lookup"><span data-stu-id="09f25-110">Use Group Policy to configure protocol recognition</span></span>

1. <span data-ttu-id="09f25-111">グループ ポリシー管理エンドポイントで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="09f25-111">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="09f25-112">[コンピューターの **構成]**  >  **[管理用**  >  **テンプレート] Windowsネットワーク**  >  **Microsoft Defender ウイルス対策**  >  **システム] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="09f25-112">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="09f25-113">プロトコル **認識を選択します**。</span><span class="sxs-lookup"><span data-stu-id="09f25-113">Select **protocol recognition**.</span></span> <span data-ttu-id="09f25-114">既定では、この設定は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="09f25-114">By default, this policy is enabled.</span></span> <span data-ttu-id="09f25-115">[構成されていません **] を設定すると**、定義の削除が有効になります。</span><span class="sxs-lookup"><span data-stu-id="09f25-115">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="09f25-116">ポリシーを編集するには、[ポリシー設定の **編集] リンクを選択** します。</span><span class="sxs-lookup"><span data-stu-id="09f25-116">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="09f25-117">[有効 **] を** 選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="09f25-117">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="09f25-118">更新されたグループ ポリシー オブジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="09f25-118">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="09f25-119">「 [グループ ポリシー管理コンソール」を参照してください](/windows/win32/srvnodes/group-policy)。</span><span class="sxs-lookup"><span data-stu-id="09f25-119">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="09f25-120">オンプレミスでグループ ポリシー オブジェクトを使用していますか?</span><span class="sxs-lookup"><span data-stu-id="09f25-120">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="09f25-121">クラウドでの翻訳方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="09f25-121">See how they translate in the cloud.</span></span> <span data-ttu-id="09f25-122">[[プレビュー] でグループ ポリシー分析を使用して、オンプレミスのグループ ポリシー Microsoft エンドポイント マネージャーを分析します](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="09f25-122">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="09f25-123">関連記事</span><span class="sxs-lookup"><span data-stu-id="09f25-123">Related articles</span></span>

- [<span data-ttu-id="09f25-124">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="09f25-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="09f25-125">クラウドによる保護の有効化</span><span class="sxs-lookup"><span data-stu-id="09f25-125">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="09f25-126">マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス</span><span class="sxs-lookup"><span data-stu-id="09f25-126">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)