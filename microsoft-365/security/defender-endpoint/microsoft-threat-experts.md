---
title: Microsoft 脅威エキスパート
ms.reviewer: ''
description: Microsoft 脅威エキスパートは、Microsoft Defender for Endpoint に追加の専門知識を提供します。
keywords: 管理された脅威の検出サービス、管理された脅威の検出、管理された検出と応答 (MDR) サービス、MTE、Microsoft 脅威エキスパート、MTE-TAN、標的型攻撃通知、標的型攻撃通知
search.product: Windows 10
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 956fb591154df374c8010d875645e1122f3419b2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879242"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="14124-104">Microsoft 脅威エキスパート</span><span class="sxs-lookup"><span data-stu-id="14124-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="14124-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="14124-105">**Applies to:**</span></span>
- [<span data-ttu-id="14124-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="14124-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="14124-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14124-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="14124-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="14124-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="14124-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="14124-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="14124-110">Microsoft 脅威エキスパートは、セキュリティ運用センター (SOC) に専門家レベルの監視と分析を提供し、固有の環境における重大な脅威を見逃しなくするための管理された脅威検出サービスです。</span><span class="sxs-lookup"><span data-stu-id="14124-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="14124-111">この管理された脅威の追求サービスは、標的型攻撃通知とオンデマンドの専門家へのアクセスという 2 つの機能を通じて、エキスパート主導のインサイトとデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="14124-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="14124-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="14124-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="14124-113">管理対象の脅威ハンティング サービスに適用する前に、Microsoft Technical Service プロバイダーおよびアカウント チームと適格性要件について話し合います。</span><span class="sxs-lookup"><span data-stu-id="14124-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="14124-114">Microsoft Defender for Endpoint のお客様の場合は **、Microsoft 脅威エキスパート -** ターゲット攻撃通知を申請して、環境内で最も重大な脅威を特定し、迅速に対応するために役立つ特別な分析情報と分析を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14124-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly.</span></span>

<span data-ttu-id="14124-115">[ターゲット攻撃Microsoft 脅威エキスパート通知] の特典に登録するには、「設定 エンドポイントの一般的な高度な機能Microsoft 脅威エキスパート - ターゲット攻撃通知を適用する」に  >    >    >    >  移動します。</span><span class="sxs-lookup"><span data-stu-id="14124-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **Endpoints** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="14124-116">承認されると、標的型攻撃通知の特典が提供されます。</span><span class="sxs-lookup"><span data-stu-id="14124-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="14124-117">**Microsoft 脅威エキスパート - Experts on Demand** を購読するには、アカウント チームまたは Microsoft 担当者に問い合わせ、組織が直面している関連する検出および敵対者について脅威の専門家と相談してください。</span><span class="sxs-lookup"><span data-stu-id="14124-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="14124-118">詳細については[、「configure Microsoft 脅威エキスパート機能」](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14124-118">See [Configure Microsoft Threat Experts capabilities](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="14124-119">Microsoft 脅威エキスパート - ターゲット攻撃通知</span><span class="sxs-lookup"><span data-stu-id="14124-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="14124-120">Microsoft 脅威エキスパート - 標的型攻撃通知は、人間の敵対的侵入、ハンズオンキーボード攻撃、サイバースパイなどの高度な攻撃など、ネットワークに対する最も重要な脅威を積極的に検出します。</span><span class="sxs-lookup"><span data-stu-id="14124-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="14124-121">これらの通知は、新しいアラートとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="14124-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="14124-122">管理されたハンティング サービスには、次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="14124-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="14124-123">脅威の監視と分析、ビジネスの滞留時間とリスクの削減</span><span class="sxs-lookup"><span data-stu-id="14124-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="14124-124">既知の攻撃と未知の攻撃の両方を検出して優先順位を付ける、ハンタートレーニングを受けた人工知能</span><span class="sxs-lookup"><span data-stu-id="14124-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="14124-125">最も重要なリスクを特定し、SOC が時間とエネルギーを最大化するのを支援する</span><span class="sxs-lookup"><span data-stu-id="14124-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="14124-126">迅速な SOC 応答を可能にするために、妥協範囲とコンテキストを迅速に提供できます。</span><span class="sxs-lookup"><span data-stu-id="14124-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="14124-127">Microsoft 脅威エキスパート - エキスパート オンデマンド</span><span class="sxs-lookup"><span data-stu-id="14124-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="14124-128">お客様は、迅速かつ正確な対応のために、Microsoft Defender セキュリティ センターから直接セキュリティ専門家に問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="14124-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="14124-129">専門家は、アラートの問い合わせ、潜在的に侵害されたデバイス、疑わしいネットワーク接続の根本原因、継続的な高度な永続的な脅威キャンペーンに関する追加の脅威インテリジェンスまで、組織に影響を与える複雑な脅威をより深く理解するために必要な洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="14124-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="14124-130">この機能を使用すると、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="14124-130">With this capability, you can:</span></span>
- <span data-ttu-id="14124-131">インシデントの根本原因や範囲を含むアラートに関する追加の明確化を取得する</span><span class="sxs-lookup"><span data-stu-id="14124-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="14124-132">高度な攻撃者に直面した場合、疑わしいデバイスの動作と次の手順をわかりやすくする</span><span class="sxs-lookup"><span data-stu-id="14124-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="14124-133">脅威のアクター、キャンペーン、または新しい攻撃者の手法に関するリスクと保護を決定する</span><span class="sxs-lookup"><span data-stu-id="14124-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="14124-134">脅威の専門家 **に相談** するオプションは、ポータルのいくつかの場所で利用できます。調査のコンテキストで専門家と対話できます。</span><span class="sxs-lookup"><span data-stu-id="14124-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="14124-135"><i>**[ヘルプとサポート] メニュー**</i></span><span class="sxs-lookup"><span data-stu-id="14124-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="14124-136">![MTE-EOD メニュー オプションのスクリーンショット](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="14124-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="14124-137"><i>**[デバイス ページのアクション] メニュー**</i></span><span class="sxs-lookup"><span data-stu-id="14124-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="14124-138">![MTE-EOD デバイス ページのアクション メニュー オプションのスクリーンショット](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="14124-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="14124-139"><i>**[アラート ページのアクション] メニュー**</i></span><span class="sxs-lookup"><span data-stu-id="14124-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="14124-140">![MTE-EOD アラート ページのアクション メニュー オプションのスクリーンショット](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="14124-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="14124-141"><i>**[ファイル ページのアクション] メニュー**</i></span><span class="sxs-lookup"><span data-stu-id="14124-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="14124-142">![MTE-EOD ファイル ページのアクション メニュー オプションのスクリーンショット](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="14124-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="14124-143">Microsoft Services Hub を通じてエキスパート オンデマンド ケースの状態を追跡する場合は、テクニカル アカウント マネージャーに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="14124-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="14124-144">Microsoft Services Hub の概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="14124-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="14124-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="14124-145">Related topic</span></span>
- [<span data-ttu-id="14124-146">機能Microsoft 脅威エキスパート構成する</span><span class="sxs-lookup"><span data-stu-id="14124-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)
