---
title: 攻撃シミュレーション トレーニングの使用を開始する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理者は、攻撃シミュレーション トレーニングを使用して、Microsoft 365 E5 または Microsoft Defender でシミュレートされたフィッシング攻撃とパスワード攻撃を実行して、Office 365プラン 2 組織に対して実行する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad86f77399cfa2a3a780d3fed7e483e3c11bc08d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082902"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="85b56-103">攻撃シミュレーション トレーニングの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="85b56-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="85b56-104">**Microsoft** Defender for [Office 365プラン 2 に適用されます](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="85b56-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="85b56-105">組織に Microsoft 365 E5 または Microsoft Defender for Office 365 Plan 2 (脅威[](office-365-ti.md)調査と対応機能を含む) がある場合は、Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニングを使用して、組織で現実的な攻撃シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="85b56-105">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="85b56-106">これらのシミュレートされた攻撃は、実際の攻撃が一番下の行に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="85b56-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="85b56-107">詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85b56-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="85b56-108">攻撃シミュレーション トレーニングは、Microsoft [Defender](attack-simulator.md)の攻撃シミュレーターで説明されている古い攻撃シミュレーター v1 エクスペリエンスに代わるOffice 365。</span><span class="sxs-lookup"><span data-stu-id="85b56-108">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="85b56-109">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="85b56-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="85b56-110">Microsoft 365 Defender ポータルを開くには、<https://security.microsoft.com> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="85b56-110">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="85b56-111">攻撃シミュレーション のトレーニングは、メールと **コラボレーションの攻撃シミュレーション** \> **トレーニングで利用できます**。</span><span class="sxs-lookup"><span data-stu-id="85b56-111">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="85b56-112">攻撃シミュレーション のトレーニングに直接移動するには、を開きます <https://security.microsoft.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="85b56-112">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="85b56-113">さまざまなサブスクリプション間で攻撃シミュレーション トレーニングを利用Microsoft 365詳細については[、「Microsoft Defender for Office 365」を参照してください](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="85b56-113">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="85b56-114">この記事の手順を実行するには、Microsoft 365 Defenderポータルまたは Azure Active Directoryでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="85b56-114">You need to be assigned permissions in the Microsoft 365 Defender portal or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="85b56-115">具体的には、組織の管理、セキュリティ管理者、または次のいずれかの役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="85b56-115">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="85b56-116">**攻撃シミュレーターの管理者**: 攻撃シミュレーション キャンペーンのすべての側面を作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="85b56-116">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="85b56-117">**攻撃シミュレータペイロード作成者**: 管理者が後で開始できる攻撃ペイロードを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b56-117">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="85b56-118">詳細については、「管理者ポータル[のアクセス許可」または「Microsoft 365 Defenderロール](permissions-microsoft-365-security-center.md)[について」を参照してください](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="85b56-118">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="85b56-119">攻撃シミュレーション トレーニングに対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="85b56-119">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="85b56-120">攻撃シミュレーションとトレーニング関連データは、他の顧客データと一緒に保存され、Microsoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="85b56-120">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="85b56-121">詳細については、「データ[の場所Microsoft 365を参照してください](../../enterprise/o365-data-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="85b56-121">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="85b56-122">攻撃シミュレーションは、NAM、APC、EUR、IND、CAN、AUS、FRA、GBR、JPN、および KOR の領域で使用できます。</span><span class="sxs-lookup"><span data-stu-id="85b56-122">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

- <span data-ttu-id="85b56-123">2021 年 6 月 15 日現在、攻撃シミュレーション のトレーニングは、GCC。</span><span class="sxs-lookup"><span data-stu-id="85b56-123">As of June 15 2021, Attack simulation training is available in GCC.</span></span> <span data-ttu-id="85b56-124">組織に Office 365 G5 GCC または Microsoft Defender for Office 365 (プラン 2) がある場合は、Microsoft 365 Defender ポータルの攻撃シミュレーション トレーニングを使用して、この記事で説明したように、組織で現実的な攻撃シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="85b56-124">If your organization has Office 365 G5 GCC or Microsoft Defender for Office 365 (Plan 2) for Government, you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization as described in this article.</span></span> <span data-ttu-id="85b56-125">攻撃シミュレーションのトレーニングは、High 環境または DoD 環境GCCまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="85b56-125">Attack simulation training is not yet available in GCC High or DoD environments.</span></span>

> [!NOTE]
> <span data-ttu-id="85b56-126">攻撃シミュレーショントレーニングは、E3 のお客様に試用版として機能のサブセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="85b56-126">Attack simulation training offers a subset of capabilities to E3 customers as a trial.</span></span> <span data-ttu-id="85b56-127">試用版には、Credential Harvest ペイロードを使用する機能と、'ISA フィッシング' または 'マス マーケット フィッシング' トレーニング エクスペリエンスを選択する機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="85b56-127">The trial offering contains the ability to use a Credential Harvest payload and the ability to select 'ISA Phishing' or 'Mass Market Phishing' training experiences.</span></span> <span data-ttu-id="85b56-128">他の機能は、E3 試用版の一部です。</span><span class="sxs-lookup"><span data-stu-id="85b56-128">No other capabilities are part of the E3 trial offering.</span></span>

## <a name="simulations"></a><span data-ttu-id="85b56-129">シミュレーション</span><span class="sxs-lookup"><span data-stu-id="85b56-129">Simulations</span></span>

<span data-ttu-id="85b56-130">*フィッシングは* 、正当な送信者または信頼できる送信者から見えるメッセージの機密情報を盗もうとする電子メール攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="85b56-130">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="85b56-131">*フィッシングは* 、ソーシャル エンジニアリングとして分類される手法のサブセットの _一部です_。</span><span class="sxs-lookup"><span data-stu-id="85b56-131">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="85b56-132">攻撃シミュレーション トレーニングでは、次の複数の種類のソーシャル エンジニアリング手法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="85b56-132">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="85b56-133">**資格情報の取得**: 攻撃者は、URL を含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="85b56-133">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="85b56-134">受信者が URL をクリックすると、通常、ユーザーにユーザー名とパスワードを求めるダイアログ ボックスが表示される Web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="85b56-134">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="85b56-135">通常、ユーザーへの信頼を構築するために、宛先ページは既知の Web サイトを表すのが主な設定です。</span><span class="sxs-lookup"><span data-stu-id="85b56-135">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="85b56-136">**マルウェアの添付** ファイル : 攻撃者は、添付ファイルを含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="85b56-136">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="85b56-137">受信者が添付ファイルを開くと、任意のコード (マクロなど) がユーザーのデバイスで実行され、攻撃者が追加のコードをインストールしたり、自分自身をさらに定着させることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="85b56-137">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="85b56-138">**添付ファイルのリンク**: これは資格情報の収集のハイブリッドです。</span><span class="sxs-lookup"><span data-stu-id="85b56-138">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="85b56-139">攻撃者は、添付ファイル内の URL を含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="85b56-139">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="85b56-140">受信者が添付ファイルを開き、URL をクリックすると、通常、ユーザーにユーザー名とパスワードを求めるダイアログ ボックスが表示される Web サイトに移動されます。</span><span class="sxs-lookup"><span data-stu-id="85b56-140">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="85b56-141">通常、ユーザーへの信頼を構築するために、宛先ページは既知の Web サイトを表すのが主な設定です。</span><span class="sxs-lookup"><span data-stu-id="85b56-141">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="85b56-142">**マルウェアへのリンク**: 攻撃者は、既知のファイル共有サイト (たとえば、SharePoint Online または Dropbox) の添付ファイルへのリンクを含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="85b56-142">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="85b56-143">受信者が URL をクリックすると、添付ファイルが開き、任意のコード (マクロなど) がユーザーのデバイス上で実行され、攻撃者が追加のコードをインストールしたり、自分自身をさらに定着させることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="85b56-143">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="85b56-144">**ドライブバイ URL**: 攻撃者は、URL を含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="85b56-144">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="85b56-145">受信者が URL をクリックすると、バックグラウンド コードを実行しようとする Web サイトにアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="85b56-145">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="85b56-146">このバックグラウンド コードは、受信者に関する情報を収集したり、デバイスに任意のコードを展開したりします。</span><span class="sxs-lookup"><span data-stu-id="85b56-146">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="85b56-147">通常、リンク先の Web サイトは、侵害された既知の Web サイトまたは既知の Web サイトの複製です。</span><span class="sxs-lookup"><span data-stu-id="85b56-147">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="85b56-148">Web サイトに関する理解は、リンクが安全にクリックできるとユーザーに理解を深めさせるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="85b56-148">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="85b56-149">この手法は、ウォーターホール攻撃 _とも呼ばれる。_</span><span class="sxs-lookup"><span data-stu-id="85b56-149">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="85b56-150">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーでシミュレートされたフィッシング URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="85b56-150">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="85b56-151">多くの URL レピュテーション ベンダーと一緒に、これらのシミュレーション URL を常に許可しますが、必ずしも完全な範囲 (Google セーフ ブラウズなど) を持つとは限らない。</span><span class="sxs-lookup"><span data-stu-id="85b56-151">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="85b56-152">ほとんどのベンダーは、特定の URL (たとえば) を常に許可できるガイダンスを提供します <https://support.google.com/chrome/a/answer/7532419> 。</span><span class="sxs-lookup"><span data-stu-id="85b56-152">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="85b56-153">攻撃シミュレーション トレーニングで使用される URL については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="85b56-153">The URLs that are used by Attack simulation training are described in the following list:</span></span>

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a><span data-ttu-id="85b56-154">シミュレーションの作成</span><span class="sxs-lookup"><span data-stu-id="85b56-154">Create a simulation</span></span>

<span data-ttu-id="85b56-155">新しいシミュレーションを作成して送信する方法の手順については、「フィッシング攻撃をシミュレートする [」を参照してください](attack-simulation-training.md)。</span><span class="sxs-lookup"><span data-stu-id="85b56-155">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="85b56-156">ペイロードの作成</span><span class="sxs-lookup"><span data-stu-id="85b56-156">Create a payload</span></span>

<span data-ttu-id="85b56-157">シミュレーション内で使用するペイロードを作成する方法の手順については、「Create a custom payload for Attack Simulation [training」を参照してください](attack-simulation-training-payloads.md)。</span><span class="sxs-lookup"><span data-stu-id="85b56-157">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="85b56-158">分析情報の取得</span><span class="sxs-lookup"><span data-stu-id="85b56-158">Gaining insights</span></span>

<span data-ttu-id="85b56-159">レポートで分析情報を得る方法の手順については、「攻撃シミュレーション トレーニングを通じてインサイトを得る [」を参照してください](attack-simulation-training-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="85b56-159">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="85b56-160">攻撃シミュレーターでは、Office 365 用 Defender の セーフ リンクを使用して、フィッシング キャンペーンのターゲット受信者に送信されるペイロード メッセージ内の URL のクリック データを安全に追跡します。セーフ Links ポリシーの [ユーザークリックを追跡しない] 設定がオンになっている場合でもです。</span><span class="sxs-lookup"><span data-stu-id="85b56-160">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>
