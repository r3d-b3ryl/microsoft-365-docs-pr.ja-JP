---
title: ユーザーの定義の削除を有効Microsoft Defender ウイルス対策
description: ユーザーの定義の削除を有効Microsoft Defender ウイルス対策。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、ディフェンダー、定義の削除
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
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296480"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="73c88-104">定義の削除を有効にする</span><span class="sxs-lookup"><span data-stu-id="73c88-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="73c88-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="73c88-105">**Applies to:**</span></span>

- [<span data-ttu-id="73c88-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="73c88-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="73c88-107">グループ ポリシーを使用して定義の削除を構成できます。</span><span class="sxs-lookup"><span data-stu-id="73c88-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="73c88-108">定義の削除は、特定の脆弱性からコンピューターを保護するために必要なセキュリティ更新プログラムがコンピューターに存在する場合にチェックします。</span><span class="sxs-lookup"><span data-stu-id="73c88-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="73c88-109">システムが定義によって検出された悪用に対して脆弱ではない場合、その定義は "廃止" されます。</span><span class="sxs-lookup"><span data-stu-id="73c88-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="73c88-110">特定のプロトコルのすべてのセキュリティ インテリジェンスが廃止された場合、そのプロトコルは解析されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="73c88-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="73c88-111">この機能を有効にすると、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="73c88-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="73c88-112">最新のセキュリティ更新プログラムが適用されているコンピューターでは、ネットワーク保護はネットワークのパフォーマンスに影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="73c88-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="73c88-113">グループ ポリシーを使用して定義の削除を構成する</span><span class="sxs-lookup"><span data-stu-id="73c88-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="73c88-114">グループ ポリシー管理エンドポイントで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="73c88-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="73c88-115">[コンピューターの **構成]**  >  **[管理用**  >  **テンプレート] Windowsネットワーク**  >  **Microsoft Defender ウイルス対策**  >  **システム] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="73c88-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="73c88-116">[定義 **の削除を有効にする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73c88-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="73c88-117">既定では、この設定は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="73c88-117">By default, this policy is enabled.</span></span> <span data-ttu-id="73c88-118">[構成されていません **] を設定すると**、定義の削除が有効になります。</span><span class="sxs-lookup"><span data-stu-id="73c88-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="73c88-119">ポリシーを編集するには、[ポリシー設定の **編集] リンクを選択** します。</span><span class="sxs-lookup"><span data-stu-id="73c88-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="73c88-120">[有効 **] を** 選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73c88-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="73c88-121">更新されたグループ ポリシー オブジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="73c88-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="73c88-122">「 [グループ ポリシー管理コンソール」を参照してください](/windows/win32/srvnodes/group-policy)。</span><span class="sxs-lookup"><span data-stu-id="73c88-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="73c88-123">オンプレミスでグループ ポリシー オブジェクトを使用していますか?</span><span class="sxs-lookup"><span data-stu-id="73c88-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="73c88-124">クラウドでの翻訳方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="73c88-124">See how they translate in the cloud.</span></span> <span data-ttu-id="73c88-125">[[プレビュー] でグループ ポリシー分析を使用して、オンプレミスのグループ ポリシー Microsoft エンドポイント マネージャーを分析します](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="73c88-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="73c88-126">関連記事</span><span class="sxs-lookup"><span data-stu-id="73c88-126">Related articles</span></span>

- [<span data-ttu-id="73c88-127">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="73c88-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="73c88-128">クラウドによる保護の有効化</span><span class="sxs-lookup"><span data-stu-id="73c88-128">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="73c88-129">マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス</span><span class="sxs-lookup"><span data-stu-id="73c88-129">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)