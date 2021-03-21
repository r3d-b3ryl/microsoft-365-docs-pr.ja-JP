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
description: 管理者は、攻撃シミュレーション トレーニングを使用して、Microsoft 365 E5 または Microsoft Defender for Office 365 Plan 2 組織でシミュレートされたフィッシング攻撃とパスワード攻撃を実行する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e344153ef433bc13b16136e584ec4da73fcef6a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921350"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="da868-103">攻撃シミュレーション トレーニングの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="da868-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="da868-104">組織に脅威の調査と応答機能を含む Office 365 プラン 2 の Microsoft [](office-365-ti.md)365 E5 または Microsoft Defender がある場合は、Microsoft セキュリティ センターの攻撃シミュレーション トレーニングを使用して、組織内で現実的な攻撃シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="da868-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="da868-105">これらのシミュレートされた攻撃は、実際の攻撃が一番下の行に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="da868-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="da868-106">詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da868-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="da868-107">攻撃シミュレーション トレーニングは、Microsoft Defender の攻撃シミュレーター for Office 365 で説明されている古い攻撃シミュレーター [v1 エクスペリエンスに置き換Officeします](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="da868-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="da868-108">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="da868-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="da868-109">Microsoft セキュリティ センターを開くには、 に移動します <https://security.microsoft.com/> 。</span><span class="sxs-lookup"><span data-stu-id="da868-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="da868-110">攻撃シミュレーション のトレーニングは、メールと **コラボレーションの攻撃シミュレーション** \> **トレーニングで利用できます**。</span><span class="sxs-lookup"><span data-stu-id="da868-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="da868-111">攻撃シミュレーション のトレーニングに直接移動するには、を開きます <https://security.microsoft.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="da868-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="da868-112">さまざまな Microsoft 365 サブスクリプションでの攻撃シミュレーション トレーニングの可用性の詳細については [、「Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)サービスの説明」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da868-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="da868-113">この記事の手順を実行するには、セキュリティ & コンプライアンス センターまたは Azure Active Directory でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="da868-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="da868-114">具体的には、組織の管理、セキュリティ管理者、または次のいずれかの役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="da868-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="da868-115">**攻撃シミュレーターの管理者**: 攻撃シミュレーション キャンペーンのすべての側面を作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="da868-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="da868-116">**攻撃シミュレータペイロード作成者**: 管理者が後で開始できる攻撃ペイロードを作成します。</span><span class="sxs-lookup"><span data-stu-id="da868-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="da868-117">詳細については、「セキュリティ コンプライアンス センター [のアクセス](permissions-in-the-security-and-compliance-center.md) 許可」または「&について [」を参照してください](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="da868-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="da868-118">攻撃シミュレーション トレーニングに対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="da868-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="da868-119">攻撃シミュレーションとトレーニング関連データは、Microsoft 365 サービスの他の顧客データと一緒に保存されます。</span><span class="sxs-lookup"><span data-stu-id="da868-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="da868-120">詳細については [、「Microsoft 365 データの場所」を参照してください](../../enterprise/o365-data-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="da868-120">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="da868-121">攻撃シミュレーションは、NAM、APC、EUR、IND、CAN、AUS、FRA、GBR、JPN、および KOR の領域で使用できます。</span><span class="sxs-lookup"><span data-stu-id="da868-121">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

## <a name="simulations"></a><span data-ttu-id="da868-122">シミュレーション</span><span class="sxs-lookup"><span data-stu-id="da868-122">Simulations</span></span>

<span data-ttu-id="da868-123">*フィッシングは* 、正当な送信者または信頼できる送信者から見えるメッセージの機密情報を盗もうとする電子メール攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="da868-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="da868-124">*フィッシングは* 、ソーシャル エンジニアリングとして分類される手法のサブセットの _一部です_。</span><span class="sxs-lookup"><span data-stu-id="da868-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="da868-125">攻撃シミュレーション トレーニングでは、次の複数の種類のソーシャル エンジニアリング手法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="da868-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="da868-126">**資格情報の取得**: 攻撃者は、URL を含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="da868-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="da868-127">受信者が URL をクリックすると、通常、ユーザーにユーザー名とパスワードを求めるダイアログ ボックスが表示される Web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="da868-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="da868-128">通常、ユーザーへの信頼を構築するために、宛先ページは既知の Web サイトを表すのが主な設定です。</span><span class="sxs-lookup"><span data-stu-id="da868-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="da868-129">**マルウェアの添付** ファイル : 攻撃者は、添付ファイルを含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="da868-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="da868-130">受信者が添付ファイルを開くと、任意のコード (マクロなど) がユーザーのデバイスで実行され、攻撃者が追加のコードをインストールしたり、自分自身をさらに定着させることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="da868-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="da868-131">**添付ファイルのリンク**: これは資格情報の収集のハイブリッドです。</span><span class="sxs-lookup"><span data-stu-id="da868-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="da868-132">攻撃者は、添付ファイル内の URL を含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="da868-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="da868-133">受信者が添付ファイルを開き、URL をクリックすると、通常、ユーザーにユーザー名とパスワードを求めるダイアログ ボックスが表示される Web サイトに移動されます。</span><span class="sxs-lookup"><span data-stu-id="da868-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="da868-134">通常、ユーザーへの信頼を構築するために、宛先ページは既知の Web サイトを表すのが主な設定です。</span><span class="sxs-lookup"><span data-stu-id="da868-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="da868-135">**マルウェアへのリンク**: 攻撃者は、既知のファイル共有サイト (SharePoint Online や Dropbox など) の添付ファイルへのリンクを含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="da868-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="da868-136">受信者が URL をクリックすると、添付ファイルが開き、任意のコード (マクロなど) がユーザーのデバイス上で実行され、攻撃者が追加のコードをインストールしたり、自分自身をさらに定着させることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="da868-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="da868-137">**ドライブバイ URL**: 攻撃者は、URL を含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="da868-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="da868-138">受信者が URL をクリックすると、バックグラウンド コードを実行しようとする Web サイトにアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="da868-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="da868-139">このバックグラウンド コードは、受信者に関する情報を収集したり、デバイスに任意のコードを展開したりします。</span><span class="sxs-lookup"><span data-stu-id="da868-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="da868-140">通常、リンク先の Web サイトは、侵害された既知の Web サイトまたは既知の Web サイトの複製です。</span><span class="sxs-lookup"><span data-stu-id="da868-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="da868-141">Web サイトに関する理解は、リンクが安全にクリックできるとユーザーに理解を深めさせるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="da868-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="da868-142">この手法は、ウォーターホール攻撃 _とも呼ばれる。_</span><span class="sxs-lookup"><span data-stu-id="da868-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="da868-143">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーでシミュレートされたフィッシング URL の可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="da868-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="da868-144">多くの URL レピュテーション ベンダーと一緒にこれらのシミュレーション URL を常に許可しますが、必ずしも完全な範囲 (Google セーフ ブラウズなど) を使用できるとは限らない。</span><span class="sxs-lookup"><span data-stu-id="da868-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="da868-145">ほとんどのベンダーは、特定の URL (たとえば) を常に許可できるガイダンスを提供します <https://support.google.com/chrome/a/answer/7532419> 。</span><span class="sxs-lookup"><span data-stu-id="da868-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="da868-146">攻撃シミュレーション トレーニングで使用される URL については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="da868-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="da868-147">シミュレーションの作成</span><span class="sxs-lookup"><span data-stu-id="da868-147">Create a simulation</span></span>

<span data-ttu-id="da868-148">新しいシミュレーションを作成して送信する方法の手順については、「フィッシング攻撃をシミュレートする [」を参照してください](attack-simulation-training.md)。</span><span class="sxs-lookup"><span data-stu-id="da868-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="da868-149">ペイロードの作成</span><span class="sxs-lookup"><span data-stu-id="da868-149">Create a payload</span></span>

<span data-ttu-id="da868-150">シミュレーション内で使用するペイロードを作成する方法の手順については、「Create a custom payload for Attack Simulation [training」を参照してください](attack-simulation-training-payloads.md)。</span><span class="sxs-lookup"><span data-stu-id="da868-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="da868-151">分析情報の取得</span><span class="sxs-lookup"><span data-stu-id="da868-151">Gaining insights</span></span>

<span data-ttu-id="da868-152">レポートで分析情報を得る方法の手順については、「攻撃シミュレーション トレーニングを通じてインサイトを得る [」を参照してください](attack-simulation-training-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="da868-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="da868-153">攻撃シミュレーターは、Office 365 の Defender のセーフ リンクを使用して、フィッシング キャンペーンのターゲット受信者に送信されるペイロード メッセージ内の URL のクリック データを安全に追跡します。セーフ リンク ポリシーの [ユーザーのクリックを追跡しない] 設定がオンになっている場合でもです。</span><span class="sxs-lookup"><span data-stu-id="da868-153">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>