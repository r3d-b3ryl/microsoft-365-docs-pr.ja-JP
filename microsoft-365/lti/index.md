---
title: LTI アプリの概要
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman, sovaish
ms.date: 06/15/2021
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- M365-modern-desktop
localization_priority: None
description: M365 ラーニング ツール相互運用性 (LTI) Office アプリと、Office アプリを ラーニング 管理システム (LMS) に統合する際の教育者の支援方法について説明します。
ms.openlocfilehash: 4fd7b25b6463eec4f681e3090bb65db8b00351a8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256684"
---
# <a name="integrating-microsoft-products-with-your-learning-management-system-lms"></a><span data-ttu-id="28f0e-103">Microsoft 製品とサービス管理システム (LMS) ラーニング統合する</span><span class="sxs-lookup"><span data-stu-id="28f0e-103">Integrating Microsoft products with your Learning Management System (LMS)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="28f0e-104">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="28f0e-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="28f0e-105">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="28f0e-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

- [<span data-ttu-id="28f0e-106">OneDriveキャンバス付き LTI</span><span class="sxs-lookup"><span data-stu-id="28f0e-106">OneDrive LTI with Canvas</span></span>](#onedrive-lti-with-canvas)
- [<span data-ttu-id="28f0e-107">Teamsキャンバスを使用した会議 LTI</span><span class="sxs-lookup"><span data-stu-id="28f0e-107">Teams Meetings LTI with Canvas</span></span>](#teams-meetings-lti-with-canvas)
- [<span data-ttu-id="28f0e-108">Teamsクラス LTI</span><span class="sxs-lookup"><span data-stu-id="28f0e-108">Teams Classes LTI</span></span>](#teams-classes-lti)

<span data-ttu-id="28f0e-109">Microsoft Education とサード パーティのパートナーは、教育と学習の流れがソリューションの境界を常に越えていると理解しています。</span><span class="sxs-lookup"><span data-stu-id="28f0e-109">Microsoft Education and our third-party partners understand that the flow of teaching and learning invariably crosses solution boundaries.</span></span> <span data-ttu-id="28f0e-110">ツールをジャグルするのではなく、よりシームレスなエクスペリエンスの提供に取り組み、教育者と学習者は目標に集中しています。</span><span class="sxs-lookup"><span data-stu-id="28f0e-110">We're working on providing more seamless experiences, keeping educators and learners focused on their goals, rather than having to juggle tools.</span></span> <span data-ttu-id="28f0e-111">Microsoft 製品は、教育や学習が行われる場合はどこでも、管理システム (LMS) のラーニング統合しています。</span><span class="sxs-lookup"><span data-stu-id="28f0e-111">We're integrating Microsoft products wherever teaching and learning occurs, including within and alongside Learning Management Systems (LMS).</span></span> <span data-ttu-id="28f0e-112">LMS パートナーと協力して、microsoft の最高の機能を LMS に直接取り込む[ラーニング Tools 相互運用性 (LTI)](https://www.imsglobal.org/activity/learning-tools-interoperability)標準を使用して一連のツールを作成しました。</span><span class="sxs-lookup"><span data-stu-id="28f0e-112">We've worked with our LMS partners to create a suite of tools using the [Learning Tools Interoperability (LTI) standard](https://www.imsglobal.org/activity/learning-tools-interoperability) that brings the best of Microsoft directly into your LMS.</span></span>

<span data-ttu-id="28f0e-113">これらのツールには、新OneDrive LTI アプリ、Teams会議 LTI アプリ、および LTI アプリTeamsがあります。</span><span class="sxs-lookup"><span data-stu-id="28f0e-113">These tools include a new OneDrive LTI app, a new Teams Meetings LTI app, and a new Class Teams LTI app.</span></span> <span data-ttu-id="28f0e-114">これらの新しいツールは、安全性が高く、LTI 1.3 および LTI Advantage 標準と完全に互換性があります。</span><span class="sxs-lookup"><span data-stu-id="28f0e-114">These new tools are highly secure and fully compatible with LTI 1.3 and LTI Advantage standards.</span></span> <span data-ttu-id="28f0e-115">このOneDrive LTI アプリを使用すると、教育者と学生は、OneDrive クラウド ストレージと Office 365 ファイルを LMS 内の割り当ておよびコンテンツ作成ワークフローに直接取り込めます。</span><span class="sxs-lookup"><span data-stu-id="28f0e-115">The OneDrive LTI app allows educators and students to bring OneDrive cloud storage and Office 365 files directly into assignment and content creation workflows within an LMS.</span></span> <span data-ttu-id="28f0e-116">Teams会議 LTI アプリを使用すると、教育者と学生は、LMS 内の会議ハブ内から、Teams 会議を管理、スケジュール、およびアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="28f0e-116">The Teams Meetings LTI app allows educators and students to manage, schedule, and access their Teams Meetings from within a meetings hub in their LMS.</span></span> <span data-ttu-id="28f0e-117">Class Teams LTI アプリを使用すると、教師は、毎日の名簿更新を含む LMS コース名簿を使用して、LMS 内で自分のコースのチームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="28f0e-117">The Class Teams LTI app allows educators to create a team for their course within their LMS using the LMS course roster with daily roster updates.</span></span> <span data-ttu-id="28f0e-118">その後、学生は LMS 内からチームに直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="28f0e-118">Students can then access the team right from within the LMS.</span></span> <span data-ttu-id="28f0e-119">お客様にこれらの新しいツールを提供し、フィードバックに従ってソリューションを改善し続けていきたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="28f0e-119">We are excited to bring these new tools to customers and continue to improve our solutions according to your feedback.</span></span>

## <a name="onedrive-lti-with-canvas"></a><span data-ttu-id="28f0e-120">OneDriveキャンバス付き LTI</span><span class="sxs-lookup"><span data-stu-id="28f0e-120">OneDrive LTI with Canvas</span></span>

<span data-ttu-id="28f0e-121">ユーザー管理システム (LMS) Microsoft OneDriveをラーニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="28f0e-121">Learn more about using Microsoft OneDrive with your Learning Management System (LMS).</span></span>

- <span data-ttu-id="28f0e-122">**ワークフローにMicrosoft Office 365を直接取り込む**</span><span class="sxs-lookup"><span data-stu-id="28f0e-122">**Brings Microsoft Office 365 directly into your workflows**</span></span>

<span data-ttu-id="28f0e-123">LTI Microsoft OneDrive LTI アプリは、LMS と統合して、次のような最も重要Microsoft OneDriveワークフローにMicrosoft Office 365を直接取り込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="28f0e-123">The Microsoft OneDrive LTI app integrates with your LMS to bring Microsoft OneDrive and Microsoft Office 365 directly into your most important workflows that include:</span></span>

- <span data-ttu-id="28f0e-124">リソースの添付とコンテンツの整理。</span><span class="sxs-lookup"><span data-stu-id="28f0e-124">Attaching resources and organizing content.</span></span>
- <span data-ttu-id="28f0e-125">共同ドキュメントの開始。</span><span class="sxs-lookup"><span data-stu-id="28f0e-125">Starting collaborative documents.</span></span>
- <span data-ttu-id="28f0e-126">割り当ての作成と評価。</span><span class="sxs-lookup"><span data-stu-id="28f0e-126">Creating and grading assignments.</span></span>

- <span data-ttu-id="28f0e-127">**セキュリティで保護され、最新の LTI 標準に完全に準拠**</span><span class="sxs-lookup"><span data-stu-id="28f0e-127">**Secure and fully compliant with latest LTI standards**</span></span>

<span data-ttu-id="28f0e-128">LTI Microsoft OneDrive LTI アプリは、LTI 1.3 および LTI Advantage と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="28f0e-128">The Microsoft OneDrive LTI App is compatible with LTI 1.3 and LTI Advantage.</span></span> <span data-ttu-id="28f0e-129">この利点により、高度にセキュリティで保護され、緊密に統合されたユーザー エクスペリエンスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="28f0e-129">This advantage allows for a highly secure and tightly integrated user experience.</span></span>

- <span data-ttu-id="28f0e-130">**モダンでリッチなユーザー エクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="28f0e-130">**Modern and Rich User Experience**</span></span>

<span data-ttu-id="28f0e-131">LTI Microsoft OneDriveは、LMS エクスペリエンスに Microsoft の最高の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="28f0e-131">The Microsoft OneDrive LTI App brings the best of Microsoft right into your LMS experience.</span></span> <span data-ttu-id="28f0e-132">新しく拡張された Microsoft OneDrive ファイル ピッカーと、Office ファイルの豊富な編集エクスペリエンスを備えた、よりモダンなユーザー エクスペリエンスを提供することで、LMS の既存の Office 365 統合を改善しています。</span><span class="sxs-lookup"><span data-stu-id="28f0e-132">We're improving upon the existing Office 365 integration in your LMS by delivering a more modern user experience, complete with a new and expanded Microsoft OneDrive file picker and richer editing experiences for Office files.</span></span> <span data-ttu-id="28f0e-133">Microsoft は今後、LTI アプリMicrosoft OneDrive完全に所有します。つまり、Microsoft から自動的に最新で最高の情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="28f0e-133">Microsoft will also fully own the Microsoft OneDrive LTI App going forward, which means you’ll always get the latest and greatest from Microsoft automatically.</span></span>

<span data-ttu-id="28f0e-134">LTI Microsoft OneDriveでは、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="28f0e-134">The Microsoft OneDrive LTI App allows you to:</span></span>

- <span data-ttu-id="28f0e-135">リッチ Office 365から Word ドキュメント、プレゼンテーション、PowerPoint、Excelファイルを添付します。</span><span class="sxs-lookup"><span data-stu-id="28f0e-135">Attach Office 365 files including Word documents, PowerPoint presentations, and Excel from the Rich Content Editor.</span></span>
- <span data-ttu-id="28f0e-136">クラウドOffice 365を配布します。</span><span class="sxs-lookup"><span data-stu-id="28f0e-136">Distribute Office 365 cloud assignments.</span></span>
- <span data-ttu-id="28f0e-137">個人用ファイルとコース ファイルを表示およびMicrosoft OneDriveします。</span><span class="sxs-lookup"><span data-stu-id="28f0e-137">View and organize your personal and course Microsoft OneDrive files.</span></span>
- <span data-ttu-id="28f0e-138">コースメンバーが共有ドキュメントでリアルタイムで共同作業できるコラボレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="28f0e-138">Create collaborations where course members can work together on shared documents in real time.</span></span>
- <span data-ttu-id="28f0e-139">個人アカウントMicrosoft OneDrive学校アカウントを含む複数のアカウントにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="28f0e-139">Access multiple Microsoft OneDrive accounts, including personal and school accounts.</span></span>
- <span data-ttu-id="28f0e-140">コース モジュールOffice 365ファイルを統合します。</span><span class="sxs-lookup"><span data-stu-id="28f0e-140">Integrate Office 365 files with your course modules.</span></span>
- <span data-ttu-id="28f0e-141">LMS でシングル サインオンを行う場合は、Microsoft アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="28f0e-141">Use your Microsoft account for single sign-on with your LMS.</span></span>

<span data-ttu-id="28f0e-142">構成手順については[、「Use Microsoft OneDrive LTI with Canvas」を参照してください](use-onedrive-with-lms.md)。</span><span class="sxs-lookup"><span data-stu-id="28f0e-142">For configuration steps, see [Use Microsoft OneDrive LTI with Canvas](use-onedrive-with-lms.md).</span></span>

## <a name="teams-lti-apps"></a><span data-ttu-id="28f0e-143">TeamsLTI アプリ</span><span class="sxs-lookup"><span data-stu-id="28f0e-143">Teams LTI apps</span></span>

### <a name="teams-meetings-lti-with-canvas"></a><span data-ttu-id="28f0e-144">Teamsキャンバスを使用した会議 LTI</span><span class="sxs-lookup"><span data-stu-id="28f0e-144">Teams Meetings LTI with Canvas</span></span>

<span data-ttu-id="28f0e-145">Microsoft Teams LTI アプリを使用すると、管理者は教育機関Teamsの LMS コースに会議を組み込むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="28f0e-145">Microsoft Teams meetings LTI app helps admins incorporate Teams meetings into their educational institution's LMS course.</span></span> <span data-ttu-id="28f0e-146">教育者と学生は、過去および今後の会議を表示したり、個別または定期的な会議をスケジュールしたり、コースに関連するチーム会議に参加したりできます。すべての会議は、LMS 内から行えます。</span><span class="sxs-lookup"><span data-stu-id="28f0e-146">Educators and students can view past and upcoming meetings, schedule individual or recurring meetings, and join team meetings related to the course, all from within their LMS.</span></span>

<span data-ttu-id="28f0e-147">構成手順については[、「Use Microsoft Teams Canvas 」を参照してください](teams-meetings-with-canvas.md)。</span><span class="sxs-lookup"><span data-stu-id="28f0e-147">For configuration steps, see [Use Microsoft Teams meetings with Canvas](teams-meetings-with-canvas.md).</span></span>

### <a name="teams-classes-lti"></a><span data-ttu-id="28f0e-148">Teamsクラス LTI</span><span class="sxs-lookup"><span data-stu-id="28f0e-148">Teams Classes LTI</span></span>

<span data-ttu-id="28f0e-149">LTI Microsoft Teamsクラスは、教育者と学生が LMS と学生の間を移動Teams。</span><span class="sxs-lookup"><span data-stu-id="28f0e-149">The Microsoft Teams classes LTI app helps educators and students navigate between their LMS and Teams.</span></span> <span data-ttu-id="28f0e-150">ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="28f0e-150">Users can access their class teams associated with their course directly from within their LMS.</span></span> <span data-ttu-id="28f0e-151">構成手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="28f0e-151">You can find configuration steps below:</span></span>

- <span data-ttu-id="28f0e-152">**Teamsキャンバスを使用する LTI** クラス [Canvas Microsoft Teamsクラスを使用します](teams-classes-with-canvas.md)。</span><span class="sxs-lookup"><span data-stu-id="28f0e-152">**Teams Classes LTI with Canvas** [Use Microsoft Teams classes with Canvas](teams-classes-with-canvas.md).</span></span>
