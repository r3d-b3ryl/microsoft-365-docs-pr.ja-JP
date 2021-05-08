---
title: Microsoft Defender ウイルス対策のクラウド配信の保護レベルを指定する
description: Microsoft Defender ウイルス対策のクラウド配信保護のレベルを設定します。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、クラウド、攻撃性、保護レベル
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f441b1bd444cd70fb5b00dfcb5ebcddadf62b220
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274906"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="c49b0-104">クラウドによる保護レベルを指定する</span><span class="sxs-lookup"><span data-stu-id="c49b0-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c49b0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c49b0-105">**Applies to:**</span></span>

- [<span data-ttu-id="c49b0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c49b0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c49b0-107">Microsoft Defender Antivirus が提供するクラウド配信保護のレベルは、Microsoft Endpoint Manager (推奨) またはグループ ポリシーを使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="c49b0-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="c49b0-108">クラウド保護は、単にクラウドに保存されているファイルの保護ではありません。</span><span class="sxs-lookup"><span data-stu-id="c49b0-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="c49b0-109">Microsoft Defender Antivirus クラウド サービスは、ネットワークとデバイス (エンドポイントとも呼ばれる) に更新された保護を提供するためのメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="c49b0-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="c49b0-110">Microsoft Defender Antivirus によるクラウド保護では、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="c49b0-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="c49b0-111">Microsoft Intune と Microsoft エンドポイント マネージャーは、Microsoft エンドポイント マネージャー [の一部です](/mem/endpoint-manager-overview)。</span><span class="sxs-lookup"><span data-stu-id="c49b0-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="c49b0-112">Microsoft Endpoint Manager を使用してクラウド配信保護のレベルを指定する</span><span class="sxs-lookup"><span data-stu-id="c49b0-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="c49b0-113">Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="c49b0-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="c49b0-114">[エンドポイント **セキュリティウイルス**  >  **対策] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c49b0-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="c49b0-115">ウイルス対策プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c49b0-115">Select an antivirus profile.</span></span> <span data-ttu-id="c49b0-116">(まだプロファイルを持っていない場合、または新しいプロファイルを作成する場合は、「デバイス制限設定を Microsoft Intune で構成する」 [を参照してください](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="c49b0-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="c49b0-117">[プロパティ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c49b0-117">Select **Properties**.</span></span> <span data-ttu-id="c49b0-118">次に、[構成設定] **の横にある**[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c49b0-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="c49b0-119">[ **クラウド保護]** を展開し、[クラウド配信の保護レベル] ボックス **の一覧** で、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c49b0-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="c49b0-120">**高**: 強力なレベルの検出を適用します。</span><span class="sxs-lookup"><span data-stu-id="c49b0-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="c49b0-121">**High plus**: High level **を使用し** 、追加の保護手段を適用します (クライアントのパフォーマンスに影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="c49b0-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="c49b0-122">**ゼロ許容値**: 不明なすべての実行可能ファイルをブロックします。</span><span class="sxs-lookup"><span data-stu-id="c49b0-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="c49b0-123">[ **確認] + [保存] の** 順に選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c49b0-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="c49b0-124">いくつかのヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="c49b0-124">Need some help?</span></span> <span data-ttu-id="c49b0-125">以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c49b0-125">See the following resources:</span></span>
> - [<span data-ttu-id="c49b0-126">エンドポイント保護の構成</span><span class="sxs-lookup"><span data-stu-id="c49b0-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="c49b0-127">Intune でエンドポイント保護設定を追加する</span><span class="sxs-lookup"><span data-stu-id="c49b0-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="c49b0-128">グループ ポリシーを使用してクラウド配信保護のレベルを指定する</span><span class="sxs-lookup"><span data-stu-id="c49b0-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="c49b0-129">グループ ポリシー管理マシンで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="c49b0-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="c49b0-130">構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c49b0-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="c49b0-131">グループ ポリシー **管理エディターで、[コンピューター** の構成 **] [管理**  >  **用テンプレート] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c49b0-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="c49b0-132">ツリーを **Windows コンポーネント Microsoft** Defender ウイルス対策  >    >  **MpEngine に展開します**。</span><span class="sxs-lookup"><span data-stu-id="c49b0-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="c49b0-133">[クラウド保護レベルの **選択] 設定をダブルクリックし** 、[有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="c49b0-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="c49b0-134">保護のレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c49b0-134">Select the level of protection:</span></span>
    - <span data-ttu-id="c49b0-135">**既定のブロック レベルは** 、正当なファイルを検出するリスクを高めることなく、強力な検出を提供します。</span><span class="sxs-lookup"><span data-stu-id="c49b0-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="c49b0-136">**中程度のブロック レベル** は、高信頼検出にのみ中程度を提供します</span><span class="sxs-lookup"><span data-stu-id="c49b0-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="c49b0-137">**高ブロック レベルでは** 、クライアントのパフォーマンスを最適化しながら強力なレベルの検出を適用します (ただし、誤検知の可能性も高くなる可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="c49b0-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="c49b0-138">**高 + ブロック レベルは** 、追加の保護対策を適用します (クライアントのパフォーマンスに影響を与え、誤検知の可能性を高める可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="c49b0-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="c49b0-139">**ゼロトレランス ブロック レベルは、** 不明なすべての実行可能ファイルをブロックします。</span><span class="sxs-lookup"><span data-stu-id="c49b0-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="c49b0-140">このスイッチを High またはHigh **+** に設定すると、一部の正当なファイルが検出される可能性があります (ただし、その検出のブロックを解除または争うオプションがあります)。</span><span class="sxs-lookup"><span data-stu-id="c49b0-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="c49b0-141">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c49b0-141">Click **OK**.</span></span>

7. <span data-ttu-id="c49b0-142">更新されたグループ ポリシー オブジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="c49b0-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="c49b0-143">「 [グループ ポリシー管理コンソール」を参照してください。](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="c49b0-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="c49b0-144">オンプレミスでグループ ポリシー オブジェクトを使用していますか?</span><span class="sxs-lookup"><span data-stu-id="c49b0-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="c49b0-145">クラウドでの翻訳方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="c49b0-145">See how they translate in the cloud.</span></span> <span data-ttu-id="c49b0-146">Microsoft Endpoint Manager - Preview でグループ ポリシー分析を使用して、[オンプレミスのグループ ポリシー オブジェクトを分析します](/mem/intune/configuration/group-policy-analytics)。</span><span class="sxs-lookup"><span data-stu-id="c49b0-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="c49b0-147">関連記事</span><span class="sxs-lookup"><span data-stu-id="c49b0-147">Related articles</span></span>

- [<span data-ttu-id="c49b0-148">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="c49b0-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="c49b0-149">クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="c49b0-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c49b0-150">マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス</span><span class="sxs-lookup"><span data-stu-id="c49b0-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)