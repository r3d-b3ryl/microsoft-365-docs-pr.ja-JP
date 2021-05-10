---
title: ネットワーク トラフィック検査用の追加の定義セットを指定Microsoft Defender ウイルス対策
description: ネットワーク トラフィック検査用の追加の定義セットを指定Microsoft Defender ウイルス対策。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御者、ネットワーク トラフィック検査
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300197"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="a0ca7-104">ネットワーク トラフィック検査用の追加の定義セットを指定する</span><span class="sxs-lookup"><span data-stu-id="a0ca7-104">Specify additional definition sets for network traffic inspection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a0ca7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a0ca7-105">**Applies to:**</span></span>

- [<span data-ttu-id="a0ca7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a0ca7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a0ca7-107">グループ ポリシーを使用して、ネットワーク トラフィック検査の追加の定義セットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-107">You can specify additional definition sets for network traffic inspection using Group Policy.</span></span>

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="a0ca7-108">グループ ポリシーを使用して、ネットワーク トラフィック検査用の追加の定義セットを指定する</span><span class="sxs-lookup"><span data-stu-id="a0ca7-108">Use Group Policy to specify additional definition sets for network traffic inspection</span></span>

1. <span data-ttu-id="a0ca7-109">グループ ポリシー管理エンドポイントで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-109">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="a0ca7-110">[ネットワーク検査 **システムWindowsコンポーネントMicrosoft Defender ウイルス対策**  >    >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-110">Go to **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="a0ca7-111">[ネットワーク **トラフィック検査の追加の定義セットを指定する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-111">Select **Specify additional definition sets for network traffic inspection**.</span></span> <span data-ttu-id="a0ca7-112">既定では、このポリシーは [構成されていません] **に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-112">By default, this policy is set to **Not configured**.</span></span> 

4. <span data-ttu-id="a0ca7-113">ポリシーを編集するには、[ポリシー設定の **編集] リンクを選択** します。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-113">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="a0ca7-114">[ **有効] を** 選択し、[オプション] **セクションで** [ **表示...] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-114">Select **Enabled**, and then in the **Options** section, select **Show...**.</span></span>

6. <span data-ttu-id="a0ca7-115">リストにエントリを追加し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-115">Add entries to the list, and then select **OK**.</span></span> 

   <span data-ttu-id="a0ca7-116">各エントリは、名前と値のペアとして一覧表示する必要があります。名前は、定義セット GUID の文字列表現です。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-116">Each entry must be listed as a name-value pair, where the name is a string representation of a definition set GUID.</span></span> <span data-ttu-id="a0ca7-117">たとえば、テスト セキュリティ インテリジェンスを有効にする定義セット GUID は、次のように定義されます `{b54b6ac9-a737-498e-9120-6616ad3bf590}` 。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-117">As an example, the definition set GUID to enable test security intelligence is defined as: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`.</span></span> <span data-ttu-id="a0ca7-118">値は使用されないので、に設定することをお勧めします `0` 。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-118">The value is not used, so we recommend setting it to `0`.</span></span> 

7. <span data-ttu-id="a0ca7-119">**[OK] を** 選択し、更新されたグループ ポリシー オブジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-119">Select **OK**, and then deploy your updated Group Policy Object.</span></span> <span data-ttu-id="a0ca7-120">「 [グループ ポリシー管理コンソール」を参照してください](/windows/win32/srvnodes/group-policy)。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-120">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="a0ca7-121">オンプレミスでグループ ポリシー オブジェクトを使用していますか?</span><span class="sxs-lookup"><span data-stu-id="a0ca7-121">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="a0ca7-122">クラウドでの翻訳方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-122">See how they translate in the cloud.</span></span> <span data-ttu-id="a0ca7-123">[[プレビュー] でグループ ポリシー分析を使用して、オンプレミスのグループ ポリシー Microsoft エンドポイント マネージャーを分析します](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="a0ca7-123">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="a0ca7-124">関連記事</span><span class="sxs-lookup"><span data-stu-id="a0ca7-124">Related articles</span></span>

- [<span data-ttu-id="a0ca7-125">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="a0ca7-125">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="a0ca7-126">クラウドによる保護の有効化</span><span class="sxs-lookup"><span data-stu-id="a0ca7-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="a0ca7-127">マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス</span><span class="sxs-lookup"><span data-stu-id="a0ca7-127">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)