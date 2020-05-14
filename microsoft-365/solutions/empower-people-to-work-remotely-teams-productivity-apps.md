---
title: 4. リモートワーカーの生産性向上アプリとサービスを展開する
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Teams、Exchange、SharePoint、その他の Microsoft 365 のサービスでユーザーの生産性を向上します。
ms.openlocfilehash: dddc3cac8a6cb955e8a337eed07279ba75c029aa
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003198"
---
# <a name="4-deploy-remote-worker-productivity-apps-and-services"></a><span data-ttu-id="7bc18-103">4. リモートワーカーの生産性向上アプリとサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="7bc18-103">4. Deploy remote worker productivity apps and services</span></span>

<span data-ttu-id="7bc18-104">生産性を高めるには、コミュニケーションとコラボレーションが大切です。</span><span class="sxs-lookup"><span data-stu-id="7bc18-104">To be productive, people need to communicate and collaborate with one another.</span></span> <span data-ttu-id="7bc18-105">会議、音声、テキストでのチャット、新しいコンテンツの作成、情報やファイルの共有、メールのやりとり、予定表とタスクの管理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bc18-105">They need to meet, chat by voice and text, create new content and share information and files, exchange email, and manage calendars and tasks.</span></span> <span data-ttu-id="7bc18-106">Microsoft 365では、次のような主要な機能のすべてにクラウドベースのサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7bc18-106">Microsoft 365 provides cloud-based services for all of these key functions:</span></span>

- <span data-ttu-id="7bc18-107">離れて仕事をしていてもつながりを持つためには、Microsoft Teams を使用します。Microsoft Teams は、組織、部署、および小規模なチームや個人のために、会議、チャット、ファイルストレージの共通のコミュニケーション ハブを提供します。</span><span class="sxs-lookup"><span data-stu-id="7bc18-107">To keep people connected while they work apart, use Microsoft Teams, which provides a common hub of communication for meetings, chats, and file storage for the organization, departments, and for small teams and individuals.</span></span> 
- <span data-ttu-id="7bc18-108">メールのやりとり、予定表、連絡先、タスクを管理したりするには、Exchange Online と Outlook クライアントを使用します。</span><span class="sxs-lookup"><span data-stu-id="7bc18-108">For exchanging email and managing calendars, contacts, and tasks, use Exchange Online and the Outlook client.</span></span>
- <span data-ttu-id="7bc18-109">ファイルの保存や共同作業には、SharePoint とOneDrive を使用します。</span><span class="sxs-lookup"><span data-stu-id="7bc18-109">For storing and collaborating on files, use SharePoint and OneDrive.</span></span> <span data-ttu-id="7bc18-110">これらはWeb ブラウザーや Teams内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-110">You can use them with a web browser or within Teams.</span></span>
- <span data-ttu-id="7bc18-111">新しいコンテンツを作成したり、既存のコンテンツに対して共同作業を行うために、Microsoft 365 アプリは、ローカル コンピューターにインストールされているバージョンの Word、PowerPoint、Excel、Outlook で、継続的な機能とセキュリティ更新プログラムを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7bc18-111">For creating new content or collaborating on existing content, Microsoft 365 Apps are versions of Word, PowerPoint, Excel, and Outlook that are installed on your local computer and receive ongoing feature and security updates.</span></span>

## <a name="keep-people-connected-with-microsoft-teams"></a><span data-ttu-id="7bc18-112">Microsoft Teams を使用してつながり続ける</span><span class="sxs-lookup"><span data-stu-id="7bc18-112">Keep people connected with Microsoft Teams</span></span>

<span data-ttu-id="7bc18-113">Teams を使うことで、チャット、会議、通話、共同作業をすべて1つの場所で行えます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-113">Teams allows you to chat, meet, call, and collaborate all in one place.</span></span> <span data-ttu-id="7bc18-114">チームワークのリモートワークに必要なものがすべてまとまったハブとなっているため、何百万人ものユーザーが毎日 Teams で仕事をこなしています。</span><span class="sxs-lookup"><span data-stu-id="7bc18-114">Millions of people get their work done in Teams every day because it brings together everything you need to work remotely into a hub for teamwork.</span></span> 

<span data-ttu-id="7bc18-115">Teamsを使用してリモートワーカーをサポートする方法については、[この記事](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams) を参照ください。</span><span class="sxs-lookup"><span data-stu-id="7bc18-115">You can use [this article](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams) for guidance on supporting your remote workers with Teams.</span></span> 

### <a name="chat-and-conversations"></a><span data-ttu-id="7bc18-116">チャットと会話</span><span class="sxs-lookup"><span data-stu-id="7bc18-116">Chat and conversations</span></span>

<span data-ttu-id="7bc18-117">チャットとスレッド会話は、Teams の中核的な役割で、1 対 1 のチャットとグループのチャットや会話をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7bc18-117">Chat and threaded conversations are at the center of Teams with support for individual 1:1 chats and group chats and conversations.</span></span> <span data-ttu-id="7bc18-118">リモート ワーカーは、グループのチャットや 1 対 1 のメッセージで、GIF、ステッカー、絵文字を使用して情報、意見、自分らしさを共有できます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-118">Remote workers can share information, opinions, and personality by using gifs, stickers, and emojis in group chats or one-to-one messages.</span></span>

### <a name="meetings-and-conferencing"></a><span data-ttu-id="7bc18-119">ミーティングと会議</span><span class="sxs-lookup"><span data-stu-id="7bc18-119">Meetings and conferencing</span></span> 

<span data-ttu-id="7bc18-120">Teams は、リモートワーカーとコミュニケーションと情報共有を確実に維持できるようになります。特に、Teams では最大250人が参加できる会議を開催することもできます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-120">Teams can certainly help maintain communications and information sharing with remote workers, especially with meetings that support up to 250 people.</span></span> <span data-ttu-id="7bc18-121">Teams 会議を使用すると、組織の内外の人との対話的な共同会議を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-121">Teams meetings enable interactive, collaborative meetings with people inside and outside your organization.</span></span> <span data-ttu-id="7bc18-122">リモートワーカーは、定期的なプロジェクトのチェックポイント、同僚との意見交換、ブレーンストーミング セッション、顧客との会話のファシリテートなど、日常業務のためのTeams 会議を利用できます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-122">Remote workers can use Teams meetings for day-to-day activities including recurring project checkpoints, catching-up with colleagues, brainstorming sessions, and facilitating conversations with customers.</span></span> 

### <a name="calling"></a><span data-ttu-id="7bc18-123">通話</span><span class="sxs-lookup"><span data-stu-id="7bc18-123">Calling</span></span>

<span data-ttu-id="7bc18-124">Teamsは、フェデレーションを使用して、ユーザーと他の組織との間の直接の VoIP 通話をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7bc18-124">Teams supports direct VoIP calling between users and even other organizations using federation.</span></span> <span data-ttu-id="7bc18-125">この機能では、会議と同じコーデックが使用されます。また、PSTN 課金なしで、世界中に素晴らしいオーディオを提供します。</span><span class="sxs-lookup"><span data-stu-id="7bc18-125">It uses the same codecs as meetings and provide great audio world-wide without additional PSTN charges.</span></span> <span data-ttu-id="7bc18-126">ただし、リモートで作業している場合、外線通話を受けるために一部のユーザーは専用の電話番号が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="7bc18-126">However, some users may need a dedicated phone number to take external calls when working remotely.</span></span> <span data-ttu-id="7bc18-127">Teams は、外線通話が必要なユーザーが電話をかけたり受けたりするためのクラウド電話サービスを迅速に提供できます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-127">Teams can quickly provide cloud phone service for these users to make and receive phone calls.</span></span>

### <a name="apps-and-workflows"></a><span data-ttu-id="7bc18-128">アプリとワークフロー</span><span class="sxs-lookup"><span data-stu-id="7bc18-128">Apps and workflows</span></span>

<span data-ttu-id="7bc18-129">デスクトップ、Web、モバイルバージョンのTeams からアクセスできるアプリやワークフローのプラットフォームを提供しています。</span><span class="sxs-lookup"><span data-stu-id="7bc18-129">Teams provides a platform for apps and workflows that can be accessed from the desktop, web, and mobile versions of Teams.</span></span> <span data-ttu-id="7bc18-130">Teams には、Microsoft とサード パーティが公開する数百のアプリがあり、ユーザー参加の促進、生産性のサポート、および一般に使用されるビジネス サービスの Teams への統合のために使用できます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-130">Teams provides hundreds of apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="7bc18-131">ユーザーと管理者は、低コードの Power App および Power online の開発ツールを使用して、 Teams にカスタムアプリや自動ワークフローを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-131">Users and Admins can also create custom apps and automated workflows for Teams using the low-code Power Apps and Power Automate development tools.</span></span>

<span data-ttu-id="7bc18-132">アプリやワークフローを使用すると、重要な情報を収集して共有、反復するタスクを自動化、対話型の bot とのチャットを行うことができるので、Teams はリモートワーカーの生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-132">Apps and workflows let remote workers be more productive in Teams, by collecting and sharing critical information, automating repetitive tasks, and allowing them to chat with interactive bot.</span></span> <span data-ttu-id="7bc18-133">アプリをチャネルまたはTeams アプリバーに固定することは、ユーザーがこれらのアプリを関連性のある領域で簡単にアクセスできるようにするための優れた方法です。管理者はアプリを固定して、すべてのユーザーが使用するべきアプリの認知と採用を促進します。</span><span class="sxs-lookup"><span data-stu-id="7bc18-133">Pinning apps to a channel or the Teams app bar is a great way for users to make these apps easily accessible in a relevant space, and admins can pin apps to drive awareness and adoption of the apps that everyone should be using.</span></span>

## <a name="exchange-email-and-manage-calendars-contacts-and-tasks-with-exchange-online-and-outlook"></a><span data-ttu-id="7bc18-134">メールをやりとりして、Exchange Online と Outlook で、予定表、連絡先、タスクを管理する</span><span class="sxs-lookup"><span data-stu-id="7bc18-134">Exchange email and manage calendars, contacts, and tasks with Exchange Online and Outlook</span></span>

<span data-ttu-id="7bc18-135">Outlook では、リモートワーカーは、メール、予定表、連絡先、タスクなどを1つの場所で一元的に管理ができるので、組織のつながりを保つことができます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-135">With Outlook, remote workers can stay connected and organized with email, calendars, contacts, tasks, and more—together in one place.</span></span> <span data-ttu-id="7bc18-136">Outlook では、ユーザーに関連する内容に基づいて、その日の進捗状況を把握して優先順位を付けます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-136">Outlook helps you stay on track and prioritize your day based on what’s relevant to you.</span></span> <span data-ttu-id="7bc18-137">Outlook では、添付ファイルを OneDrive から直接共有したり、Teams会議を計画して参加したり、予定表を表示して共有したり、他のユーザーに代理人アクセス許可を提供したりできます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-137">Outlook enables you to share attachments right from OneDrive, plan and join Teams meetings, view and share calendars, and provide delegate permissions to others.</span></span> <span data-ttu-id="7bc18-138">仕事と個人的なコミットメントの両方で、次に何が起こるのか、何に注意が必要なのかを知っておくと、リモートワーカーが重要な作業に集中できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7bc18-138">Knowing what’s coming up next across both work and personal commitments and what needs attention can help remote workers focus on what matters.</span></span> <span data-ttu-id="7bc18-139">Outlook では、リモートワーカーが時間を管理し、ファイル、組織内のユーザーなど、簡単に必要な情報を見つけるための便利な方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="7bc18-139">Outlook provides helpful ways for remote workers to manage their time and to find what they need easily, including files, people in the organization, and more.</span></span> 

## <a name="store-and-collaborate-on-files-with-sharepoint-online-and-onedrive"></a><span data-ttu-id="7bc18-140">SharePoint Online および OneDrive でファイルを保存して共同作業する</span><span class="sxs-lookup"><span data-stu-id="7bc18-140">Store and collaborate on files with SharePoint Online and OneDrive</span></span>

<span data-ttu-id="7bc18-141">リモートワーカーは、コンテンツの共同作業のために SharePoint Online と OneDrive フォルダーをクラウド内の中心的な場所として使用して、ファイルの保存と共有、共同編集、コミュニケーション、共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-141">For content collaboration, remote workers can use SharePoint Online and OneDrive folders as a central place in the cloud to store and share files, co-author, communicate, and collaborate.</span></span> <span data-ttu-id="7bc18-142">リモートワーカーは、Web ブラウザー、Teams、Office アプリからでもどこからでも安全に作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-142">Remote workers can securely work from anywhere from a web browser, from Teams, and from Office apps.</span></span>

## <a name="create-and-collaborate-on-content-with-microsoft-365-apps"></a><span data-ttu-id="7bc18-143">Microsoft 365 アプリを使ってコンテンツを作成して共同作業する</span><span class="sxs-lookup"><span data-stu-id="7bc18-143">Create and collaborate on content with Microsoft 365 Apps</span></span>

<span data-ttu-id="7bc18-144">Microsoft 365 アプリは、従業員がいつでもどこからでもシームレスに共同作業できる、エンタープライズ向けの最も生産的かつ安全な Office の環境です。</span><span class="sxs-lookup"><span data-stu-id="7bc18-144">Microsoft 365 Apps is the most productive and most secure Office experience for enterprises, allowing people to work together seamlessly from anywhere, anytime.</span></span> <span data-ttu-id="7bc18-145">リモートワーカーは、同時に複数のユーザーがいるドキュメントで共同作業を行ったり、リアルタイムでの編集や変更を確認したり、ノート PC、PC、モバイルデバイスで他のユーザーと共有編集したりできます。</span><span class="sxs-lookup"><span data-stu-id="7bc18-145">Remote workers can collaborate on a document with multiple people simultaneously, see edits and changes in real time, and coauthor with others on any laptop, PC, or mobile device.</span></span>

## <a name="admin-technical-resources-for-productivity-apps-and-services"></a><span data-ttu-id="7bc18-146">生産性向上のためのアプリとサービス向けの管理者技術リソース</span><span class="sxs-lookup"><span data-stu-id="7bc18-146">Admin technical resources for productivity apps and services</span></span>

- [<span data-ttu-id="7bc18-147">Microsoft Teams を使用してリモート ワーカーをサポートする</span><span class="sxs-lookup"><span data-stu-id="7bc18-147">Support remote workers using Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams)
- [<span data-ttu-id="7bc18-148">Teams Customer Success Kit のダウンロード</span><span class="sxs-lookup"><span data-stu-id="7bc18-148">Teams Customer Success Kit download</span></span>](https://www.microsoft.com/download/details.aspx?id=54244)
- [<span data-ttu-id="7bc18-149">Teamsを推進するためのツール</span><span class="sxs-lookup"><span data-stu-id="7bc18-149">Tools for driving Teams adoption</span></span>](https://docs.microsoft.com/microsoftteams/adopt-tools-and-downloads) 
- [<span data-ttu-id="7bc18-150">Microsoft Teams の変更管理戦略を作成する</span><span class="sxs-lookup"><span data-stu-id="7bc18-150">Create a change management strategy for Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)
- [<span data-ttu-id="7bc18-151">3 層の保護を使ったチーム</span><span class="sxs-lookup"><span data-stu-id="7bc18-151">Teams with three tiers of protection</span></span>](configure-teams-three-tiers-protection.md)

- [<span data-ttu-id="7bc18-152">Office と Office 365 についてユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="7bc18-152">Train your users on Office and Office 365</span></span>](https://support.office.com/article/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c2)
- [<span data-ttu-id="7bc18-153">Web 用 Officeを使用</span><span class="sxs-lookup"><span data-stu-id="7bc18-153">Use Office for the web</span></span>](https://support.microsoft.com/office/get-started-with-office-for-the-web-in-microsoft-365-5622c7c9-721d-4b3d-8cb9-a7276c2470e5)

## <a name="next-step"></a><span data-ttu-id="7bc18-154">次の手順</span><span class="sxs-lookup"><span data-stu-id="7bc18-154">Next step</span></span>

<span data-ttu-id="7bc18-155">[手順 5](empower-people-to-work-remotely-communication-venues.md)を続行して、新型コロナ ウイルス感染症の危機の中、固有の要件に対応できる追加のコミュニケーションの場を作成します。</span><span class="sxs-lookup"><span data-stu-id="7bc18-155">Continue with [Step 5](empower-people-to-work-remotely-communication-venues.md) to create additional communication venues that serve the unique requirements of the COVID-19 crisis.</span></span>
