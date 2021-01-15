---
title: 攻撃シミュレーション トレーニングの使用を開始する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Microsoft 365 E5 または microsoft Defender for Office 365 プラン 2 の組織で、攻撃シミュレーション トレーニングを使用してシミュレートされたフィッシングとパスワード攻撃を実行する方法について説明します。
ms.openlocfilehash: 9d97816edf7d59c002658fc8bb3f39e72dbc2430
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871250"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="44d4d-103">攻撃シミュレーション トレーニングの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="44d4d-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="44d4d-104">組織に Microsoft 365 E5 または microsoft Defender for Office 365[](office-365-ti.md)プラン 2 (脅威の調査と対応の機能を含む) がある場合は、Microsoft セキュリティ センターの攻撃シミュレーション トレーニングを使用して、組織で現実的な攻撃シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="44d4d-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="44d4d-105">これらのシミュレートされた攻撃は、実際の攻撃が下線に影響を与える前に、脆弱なユーザーを特定して見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="44d4d-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="44d4d-106">詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44d4d-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="44d4d-107">攻撃シミュレーション トレーニングは、Microsoft Defender for Office [365](attack-simulator.md)の攻撃シミュレーターで説明されている、古い攻撃シミュレーター v1 エクスペリエンスに取って代わるものになります。</span><span class="sxs-lookup"><span data-stu-id="44d4d-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="44d4d-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="44d4d-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="44d4d-109">Microsoft セキュリティ センターを開くには、次のアクセス先に移動します <https://security.microsoft.com/> 。</span><span class="sxs-lookup"><span data-stu-id="44d4d-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="44d4d-110">攻撃シミュレーション トレーニングは、電子メールとコラボレーション **の攻撃シミュレーション** \> **トレーニングで利用できます**。</span><span class="sxs-lookup"><span data-stu-id="44d4d-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="44d4d-111">直接攻撃シミュレーション トレーニングに移動するには、開きます <https://security.microsoft.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="44d4d-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="44d4d-112">さまざまな Microsoft 365 サブスクリプションで攻撃シミュレーション トレーニングを利用する方法について詳しくは、Microsoft Defender で Office [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)サービスの説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44d4d-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="44d4d-113">この記事の手順を実行する前に、セキュリティ & コンプライアンス センターまたは Azure Active Directory でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="44d4d-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="44d4d-114">具体的には、組織の管理、セキュリティ管理者、または次のいずれかの役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="44d4d-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="44d4d-115">**攻撃シミュレータ管理者**: 攻撃シミュレーション キャンペーンのすべての側面を作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="44d4d-116">**攻撃シミュレータペイロード作成者**: 管理者が後で開始できる攻撃ペイロードを作成します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="44d4d-117">詳細については、「セキュリティ/コンプライアンス センター [の](permissions-in-the-security-and-compliance-center.md) アクセス許可」または「& [について」を参照してください](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="44d4d-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="44d4d-118">攻撃シミュレーション トレーニング用の対応する PowerShell コマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="44d4d-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="44d4d-119">攻撃シミュレーションとトレーニング関連データは、Microsoft 365 サービスの他の顧客データと一緒に保存されます。</span><span class="sxs-lookup"><span data-stu-id="44d4d-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="44d4d-120">詳細については [、Microsoft 365 のデータの場所を参照してください](/microsoft-365/enterprise/o365-data-locations)。</span><span class="sxs-lookup"><span data-stu-id="44d4d-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="44d4d-121">攻撃シミュレーションは現在、SGP、NOR、UAE、ZAF、GER、BRA、CHE の地域では利用できません。</span><span class="sxs-lookup"><span data-stu-id="44d4d-121">Attack simulation is currently not available in the following regions: SGP, NOR, UAE, ZAF, GER, BRA, and CHE.</span></span>

## <a name="simulations"></a><span data-ttu-id="44d4d-122">シミュレーション</span><span class="sxs-lookup"><span data-stu-id="44d4d-122">Simulations</span></span>

<span data-ttu-id="44d4d-123">*フィッシングは* 、正当な送信者または信頼できる送信者から見えるメッセージ内の機密情報を盗もうとする電子メール攻撃の一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="44d4d-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="44d4d-124">*フィッシングは* 、ソーシャル エンジニアリングとして分類する手法のサブセットの _一部です_。</span><span class="sxs-lookup"><span data-stu-id="44d4d-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="44d4d-125">攻撃シミュレーション トレーニングでは、次の複数の種類のソーシャル エンジニアリング手法を利用できます。</span><span class="sxs-lookup"><span data-stu-id="44d4d-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="44d4d-126">**資格情報の取得**: 攻撃者は、URL を含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="44d4d-127">受信者が URL をクリックすると、通常はユーザー名とパスワードを求めるダイアログ ボックスが表示される Web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="44d4d-128">通常、宛先ページは、ユーザーの信頼を構築するために、既知の Web サイトを表すメッセージです。</span><span class="sxs-lookup"><span data-stu-id="44d4d-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="44d4d-129">**マルウェアの添付** ファイル : 攻撃者が、添付ファイルを含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="44d4d-130">受信者が添付ファイルを開くと、ユーザーのデバイスで任意のコード (マクロなど) が実行され、攻撃者が追加のコードをインストールしたり、それ自体をさらに進めることができます。</span><span class="sxs-lookup"><span data-stu-id="44d4d-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="44d4d-131">**添付ファイル内のリンク**: これは資格情報取得のハイブリッドです。</span><span class="sxs-lookup"><span data-stu-id="44d4d-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="44d4d-132">攻撃者は、添付ファイル内の URL を含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="44d4d-133">受信者が添付ファイルを開いて URL をクリックすると、通常はユーザー名とパスワードを求めるダイアログ ボックスが表示される Web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="44d4d-134">通常、宛先ページは、ユーザーの信頼を構築するために、既知の Web サイトを表すメッセージです。</span><span class="sxs-lookup"><span data-stu-id="44d4d-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="44d4d-135">**マルウェアへのリンク**: 攻撃者は、既知のファイル共有サイト (SharePoint Online や Dropbox など) 上の添付ファイルへのリンクを含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="44d4d-136">受信者が URL をクリックすると、添付ファイルが開き、ユーザーのデバイス上で任意のコード (マクロなど) が実行され、攻撃者が追加のコードをインストールしたり、自分自身をさらに進めることができます。</span><span class="sxs-lookup"><span data-stu-id="44d4d-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="44d4d-137">**ドライブバイ URL**: 攻撃者が、URL を含むメッセージを受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="44d4d-138">受信者が URL をクリックすると、バックグラウンド コードの実行を試みる Web サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="44d4d-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="44d4d-139">このバックグラウンド コードは、受信者に関する情報を収集するか、デバイスに任意のコードを展開します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="44d4d-140">通常、リンク先の Web サイトは、侵害された既知の Web サイト、または既知の Web サイトの複製です。</span><span class="sxs-lookup"><span data-stu-id="44d4d-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="44d4d-141">Web サイトに精通すると、リンクが安全にクリックできるとユーザーを説得できます。</span><span class="sxs-lookup"><span data-stu-id="44d4d-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="44d4d-142">この手法は、水の穴攻撃 _とも呼ばれる手法です_。</span><span class="sxs-lookup"><span data-stu-id="44d4d-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="44d4d-143">フィッシング キャンペーンで URL を使用する前に、サポートされている Web ブラウザーでシミュレートされたフィッシング URL の可用性を確認します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="44d4d-144">多くの URL 評価ベンダーと一緒に、これらのシミュレーション URL を常に許可しますが、必ずしも完全に対応できるとは限らない (Google セーフ ブラウズなど)。</span><span class="sxs-lookup"><span data-stu-id="44d4d-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="44d4d-145">ほとんどのベンダーは、特定の URL (たとえば) を常に許可できるガイダンスを提供します <https://support.google.com/chrome/a/answer/7532419> 。</span><span class="sxs-lookup"><span data-stu-id="44d4d-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="44d4d-146">攻撃シミュレーション トレーニングで使用される URL を次の一覧に示します。</span><span class="sxs-lookup"><span data-stu-id="44d4d-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="44d4d-147">シミュレーションを作成する</span><span class="sxs-lookup"><span data-stu-id="44d4d-147">Create a simulation</span></span>

<span data-ttu-id="44d4d-148">新しいシミュレーションを作成して送信する方法の詳しい手順については、「フィッシング攻撃をシミュレートする [」を参照してください](attack-simulation-training.md)。</span><span class="sxs-lookup"><span data-stu-id="44d4d-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="44d4d-149">ペイロードを作成する</span><span class="sxs-lookup"><span data-stu-id="44d4d-149">Create a payload</span></span>

<span data-ttu-id="44d4d-150">シミュレーション内で使用するペイロードを作成する手順については、「攻撃シミュレーション トレーニング用のカスタム ペイロードを作成する」を [参照してください](attack-simulation-training-payloads.md)。</span><span class="sxs-lookup"><span data-stu-id="44d4d-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="44d4d-151">分析情報の取得</span><span class="sxs-lookup"><span data-stu-id="44d4d-151">Gaining insights</span></span>

<span data-ttu-id="44d4d-152">レポートを使用して分析情報を得る方法の詳しい手順については、「攻撃シミュレーション トレーニングによる分析情報の取得」 [をご覧ください](attack-simulation-training-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="44d4d-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>
