---
title: 手順 5.  リモートワーカー向けの生産性向上アプリとサービスを展開する
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Teams、Exchange、SharePoint、その他の Microsoft 365 サービスを利用することで、ユーザーの生産性を向上できます。
ms.openlocfilehash: 7b62191d08e5ff91e54bb16b06a0511e02f16b6d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916180"
---
# <a name="step-5-deploy-remote-worker-productivity-apps-and-services"></a><span data-ttu-id="c45fb-104">手順 5. </span><span class="sxs-lookup"><span data-stu-id="c45fb-104">Step 5.</span></span> <span data-ttu-id="c45fb-105">リモートワーカー向けの生産性向上アプリとサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="c45fb-105">Deploy remote worker productivity apps and services</span></span>

<span data-ttu-id="c45fb-106">生産性を高めるには、リモートワーカー間のコミュニケーションとコラボレーションが重要です。</span><span class="sxs-lookup"><span data-stu-id="c45fb-106">To be productive, people need to communicate and collaborate with one another.</span></span> <span data-ttu-id="c45fb-107">会議、音声やテキストでのチャット、新しいコンテンツの作成と情報やファイルの共有、メールのやりとり、予定表やタスクの管理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c45fb-107">They need to meet, chat by voice and text, create new content and share information and files, exchange email, and manage calendars and tasks.</span></span> <span data-ttu-id="c45fb-108">Microsoft 365 は、次の主要な機能すべてをクラウドベースのサービスで実現します。</span><span class="sxs-lookup"><span data-stu-id="c45fb-108">Microsoft 365 provides cloud-based services for all of these key functions:</span></span>

| <span data-ttu-id="c45fb-109">IT 関数</span><span class="sxs-lookup"><span data-stu-id="c45fb-109">IT function</span></span> | <span data-ttu-id="c45fb-110">Microsoft 365 コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c45fb-110">Microsoft 365 components</span></span> | <span data-ttu-id="c45fb-111">説明</span><span class="sxs-lookup"><span data-stu-id="c45fb-111">Description</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="c45fb-112">メール サービス</span><span class="sxs-lookup"><span data-stu-id="c45fb-112">Email services</span></span> | <span data-ttu-id="c45fb-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c45fb-113">Exchange Online</span></span> | <span data-ttu-id="c45fb-114">Outlook クライアントを使用した、メール交換、および予定表、連絡先、タスクの管理。</span><span class="sxs-lookup"><span data-stu-id="c45fb-114">Exchange email and manage calendars, contacts, and tasks with the Outlook client.</span></span> |
| <span data-ttu-id="c45fb-115">組織のチャット、ボイス オーバー IP (VOIP)、およびチーム ベースのコラボレーション</span><span class="sxs-lookup"><span data-stu-id="c45fb-115">Organizational chat, voice over IP (VOIP), and team-based collaboration</span></span> | <span data-ttu-id="c45fb-116">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c45fb-116">Microsoft Teams</span></span> | <span data-ttu-id="c45fb-117">組織、部門、および小規模なチームや個人向けの会議、チャット、ファイル ストレージの共通のコミュニケーション ハブを使用して、離れて作業をしながら密接な連携を維持します。</span><span class="sxs-lookup"><span data-stu-id="c45fb-117">Keep people connected while they work apart with a common hub of communication for meetings, chats, and file storage for the organization, departments, and for small teams and individuals.</span></span> |
| <span data-ttu-id="c45fb-118">イントラネット サイト、ドキュメント コラボレーション</span><span class="sxs-lookup"><span data-stu-id="c45fb-118">Intranet sites, document collaboration</span></span> | <span data-ttu-id="c45fb-119">SharePoint および OneDrive</span><span class="sxs-lookup"><span data-stu-id="c45fb-119">SharePoint and OneDrive</span></span> | <span data-ttu-id="c45fb-120">Web ブラウザ内または Teams 内のファイルを保存して共同作業します。</span><span class="sxs-lookup"><span data-stu-id="c45fb-120">Store and collaborate on files within a web browser or within Teams.</span></span> |
| <span data-ttu-id="c45fb-121">デスクトップおよびモバイル デバイスの Office アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c45fb-121">Desktop and mobile device Office applications</span></span> | <span data-ttu-id="c45fb-122">Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="c45fb-122">Microsoft 365 Apps</span></span> | <span data-ttu-id="c45fb-123">ローカル コンピューターにインストールされ、継続的な機能とセキュリティの更新を受け取るバージョンの Word、PowerPoint、Excel、および Outlook を使用して、新しいコンテンツの作成や、既存のコンテンツに対しての共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="c45fb-123">Create new content or collaborate on existing content with versions of Word, PowerPoint, Excel, and Outlook that are installed on your local computer and receive ongoing feature and security updates.</span></span> |
||||

![Teams、Outlook、SharePoint、OneDrive、Microsoft 365 アプリを使用して生産性を維持する](../media/empower-people-to-work-remotely/remote-workers-productivity-grid.png)

## <a name="keep-people-connected-with-microsoft-teams"></a><span data-ttu-id="c45fb-125">Microsoft Teams を使用して密接な連携を維持する</span><span class="sxs-lookup"><span data-stu-id="c45fb-125">Keep people connected with Microsoft Teams</span></span>

<span data-ttu-id="c45fb-126">Teams を使うことで、チャット、会議、通話、共同作業をすべて 1 つの場所で行えます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-126">Teams allows you to chat, meet, call, and collaborate all in one place.</span></span> <span data-ttu-id="c45fb-127">何百万人ものユーザーが毎日 Teams で仕事をこなしています。Teams には、リモート ワークに必要なすべてのものが、チームワーク用のハブにまとめられているのです。</span><span class="sxs-lookup"><span data-stu-id="c45fb-127">Millions of people get their work done in Teams every day because it brings together everything you need to work remotely into a hub for teamwork.</span></span> 

<span data-ttu-id="c45fb-128">詳細なガイドについては、「[Microsoft Teams を使用してリモート ワーカーをサポートする](/microsoftteams/support-remote-work-with-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c45fb-128">For detailed guidance, see [Support remote workers using Microsoft Teams](/microsoftteams/support-remote-work-with-teams).</span></span> 

<span data-ttu-id="c45fb-129">Teams をリモート ワークに使用するためのガイダンスとデモについては、「[Microsoft Teams Web キャストによるハイブリッド作業の有効化](https://resources.techcommunity.microsoft.com/enabling-hybrid-work/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c45fb-129">Watch the [Enabling hybrid work with Microsoft Teams webcasts](https://resources.techcommunity.microsoft.com/enabling-hybrid-work/) for guidance and demos on using Teams for remote work.</span></span>

### <a name="chat-and-conversations"></a><span data-ttu-id="c45fb-130">チャットと会話</span><span class="sxs-lookup"><span data-stu-id="c45fb-130">Chat and conversations</span></span>

<span data-ttu-id="c45fb-131">チャットとスレッド形式の会話は、Teams の中核的な機能で、1 対 1 のチャットに加え、グループでのチャットや会話もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c45fb-131">Chat and threaded conversations are at the center of Teams with support for individual 1:1 chats and group chats and conversations.</span></span> <span data-ttu-id="c45fb-132">リモート ワーカーは、グループ チャットや 1 対 1 のメッセージで、GIF、ステッカー、絵文字を使用して情報、意見、自分らしさを共有できます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-132">Remote workers can share information, opinions, and personality by using gifs, stickers, and emojis in group chats or one-to-one messages.</span></span>

### <a name="meetings-and-conferencing"></a><span data-ttu-id="c45fb-133">ミーティングと会議</span><span class="sxs-lookup"><span data-stu-id="c45fb-133">Meetings and conferencing</span></span> 

<span data-ttu-id="c45fb-134">Teams は、リモート ワーカーとのコミュニケーションや情報共有に非常に役立ちます。特に、Teams では最大 250 人が参加できる会議を開催することもできます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-134">Teams can certainly help maintain communications and information sharing with remote workers, especially with meetings that support up to 250 people.</span></span> <span data-ttu-id="c45fb-135">Teams 会議を使用すると、組織の内外の人との対話的な共同会議を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-135">Teams meetings enable interactive, collaborative meetings with people inside and outside your organization.</span></span> <span data-ttu-id="c45fb-136">リモート ワーカーは、プロジェクトの定期チェックポイント、同僚との意見交換、ブレーンストーミング セッション、顧客との会話促進など、さまざまな日常業務で Teams 会議を利用できます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-136">Remote workers can use Teams meetings for day-to-day activities including recurring project checkpoints, catching-up with colleagues, brainstorming sessions, and facilitating conversations with customers.</span></span> 

### <a name="calling"></a><span data-ttu-id="c45fb-137">通話</span><span class="sxs-lookup"><span data-stu-id="c45fb-137">Calling</span></span>

<span data-ttu-id="c45fb-138">Teams では、フェデレーションを使用して、ユーザー間だけでなく、他の組織との間の直接の VoIP 通話もサポートします。</span><span class="sxs-lookup"><span data-stu-id="c45fb-138">Teams supports direct VoIP calling between users and even other organizations using federation.</span></span> <span data-ttu-id="c45fb-139">この機能では、会議と同じコーデックが使用されます。また、PSTN 課金なしで、世界中に高品質の音声を提供します。</span><span class="sxs-lookup"><span data-stu-id="c45fb-139">It uses the same codecs as meetings and provide great audio world-wide without additional PSTN charges.</span></span> <span data-ttu-id="c45fb-140">ただし、リモートで作業している場合、ユーザーによっては外線通話を受けるために専用の電話番号が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c45fb-140">However, some users may need a dedicated phone number to take external calls when working remotely.</span></span> <span data-ttu-id="c45fb-141">Teams は、外線通話が必要なユーザーが電話をかけたり受けたりするためのクラウド電話サービスを迅速に提供できます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-141">Teams can quickly provide cloud phone service for these users to make and receive phone calls.</span></span>

### <a name="apps-and-workflows"></a><span data-ttu-id="c45fb-142">アプリとワークフロー</span><span class="sxs-lookup"><span data-stu-id="c45fb-142">Apps and workflows</span></span>

<span data-ttu-id="c45fb-143">Teams は、デスクトップ、Web、モバイル バージョンの Teams からアクセスできるアプリやワークフローのプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="c45fb-143">Teams provides a platform for apps and workflows that can be accessed from the desktop, web, and mobile versions of Teams.</span></span> <span data-ttu-id="c45fb-144">Teams には、Microsoft やサード パーティが公開しているアプリが何百個も用意されており、ユーザー参加の促進、生産性のサポート、よく使用されるビジネス サービスの Teams への統合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-144">Teams provides hundreds of apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="c45fb-145">ユーザーと管理者は、ローコードの Power Apps および Power Automate 開発ツールを使用して、Teams 用のカスタム アプリや自動ワークフローを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-145">Users and Admins can also create custom apps and automated workflows for Teams using the low-code Power Apps and Power Automate development tools.</span></span>

<span data-ttu-id="c45fb-146">アプリやワークフローを使用すると、重要な情報の収集と共有、繰り返し実行するタスクの自動化、対話型ボットとのチャットが可能になるため、リモート ワーカーの Teams での生産性をさらに高めることができます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-146">Apps and workflows let remote workers be more productive in Teams, by collecting and sharing critical information, automating repetitive tasks, and allowing them to chat with interactive bot.</span></span> <span data-ttu-id="c45fb-147">アプリをチャネルまたは Teams アプリ バーにピン留めすることは、ユーザーがこれらのアプリを関連性のある領域で簡単にアクセスできるようにするための優れた方法です。また、管理者はアプリをピン留めすることにより、すべてのユーザーが使用する必要のあるアプリの認知と採用を促進することができます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-147">Pinning apps to a channel or the Teams app bar is a great way for users to make these apps easily accessible in a relevant space, and admins can pin apps to drive awareness and adoption of the apps that everyone should be using.</span></span>

## <a name="exchange-email-and-manage-calendars-contacts-and-tasks-with-exchange-online-and-outlook"></a><span data-ttu-id="c45fb-148">Exchange Online と Outlook を使用した、メール交換、および予定表、連絡先、タスクの管理</span><span class="sxs-lookup"><span data-stu-id="c45fb-148">Exchange email and manage calendars, contacts, and tasks with Exchange Online and Outlook</span></span>

<span data-ttu-id="c45fb-149">リモート ワーカーは、Outlook を使用することにより、メール、予定表、連絡先、タスクなどにいつでもアクセスでき、自分の予定を一元的に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-149">With Outlook, remote workers can stay connected and organized with email, calendars, contacts, tasks, and more—together in one place.</span></span> <span data-ttu-id="c45fb-150">Outlook は、ユーザーが自分に関連する内容を基に、予定どおり作業を遂行したり、1 日の作業に優先順位を付けたりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-150">Outlook helps you stay on track and prioritize your day based on what’s relevant to you.</span></span> <span data-ttu-id="c45fb-151">Outlook を使用すると、添付ファイルを OneDrive から直接共有したり、Teams 会議を計画して参加したり、予定表を表示して共有したり、他のユーザーに代理アクセス権を提供したりできます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-151">Outlook enables you to share attachments right from OneDrive, plan and join Teams meetings, view and share calendars, and provide delegate permissions to others.</span></span> <span data-ttu-id="c45fb-152">リモート ワーカーは、仕事上の責任と個人的な責任の両方について、次の予定を知り、何に注意が必要かを把握することにより、重要な問題に注意を集中できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c45fb-152">Knowing what’s coming up next across both work and personal commitments and what needs attention can help remote workers focus on what matters.</span></span> <span data-ttu-id="c45fb-153">Outlook は、リモート ワーカーが自分の時間を管理をしたり、ファイルや組織内の人物など、必要な情報を簡単に見つけたりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-153">Outlook provides helpful ways for remote workers to manage their time and to find what they need easily, including files, people in the organization, and more.</span></span> 

<span data-ttu-id="c45fb-154">組織のメールと、先進認証と条件付きアクセスをサポートするメール クライアントを保護する、推奨される ID とデバイス アクセス ポリシーについては、[こちらの記事](../security/office-365-security/secure-email-recommended-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c45fb-154">See [this article](../security/office-365-security/secure-email-recommended-policies.md) for the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and Conditional Access.</span></span>

## <a name="store-and-collaborate-on-files-with-sharepoint-and-onedrive"></a><span data-ttu-id="c45fb-155">SharePoint と OneDrive でファイルを格納して共同編集</span><span class="sxs-lookup"><span data-stu-id="c45fb-155">Store and collaborate on files with SharePoint and OneDrive</span></span>

<span data-ttu-id="c45fb-156">リモート ワーカーは、コンテンツの共同作業のために SharePoint と OneDrive フォルダーをクラウド内の中心的な場所として使用して、ファイルの保存と共有、共同編集、コミュニケーション、共同作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-156">For content collaboration, remote workers can use SharePoint and OneDrive folders as a central place in the cloud to store and share files, co-author, communicate, and collaborate.</span></span> <span data-ttu-id="c45fb-157">リモート ワーカーは、Web ブラウザー、Teams、Office アプリのどこからでも安全に作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-157">Remote workers can securely work from anywhere from a web browser, from Teams, and from Office apps.</span></span>

<span data-ttu-id="c45fb-158">以下から SharePoint か OneDrive へドキュメントを移行しなければならない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c45fb-158">You might have to migrate your documents to SharePoint or OneDrive from:</span></span>

- [<span data-ttu-id="c45fb-159">SharePoint Server チームサイト</span><span class="sxs-lookup"><span data-stu-id="c45fb-159">SharePoint Server Team Sites</span></span>](/sharepointmigration/sp-teams-sites-migration-guide)
- [<span data-ttu-id="c45fb-160">個人用サイト</span><span class="sxs-lookup"><span data-stu-id="c45fb-160">MySites</span></span>](/sharepointmigration/mysites-to-onedrive-migration-guide)
- [<span data-ttu-id="c45fb-161">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="c45fb-161">File shares</span></span>](/sharepointmigration/fileshare-to-odsp-migration-guide)
- [<span data-ttu-id="c45fb-162">ボックス</span><span class="sxs-lookup"><span data-stu-id="c45fb-162">Box</span></span>](/sharepointmigration/box-to-onedrive-and-sharepoint-migration-guide)

<span data-ttu-id="c45fb-163">SharePoint Online と OneDrive を保護するには、推奨される ID とデバイス アクセス ポリシーに関する[こちらの記事](../security/office-365-security/sharepoint-file-access-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c45fb-163">To protect SharePoint and OneDrive, see [this article](../security/office-365-security/sharepoint-file-access-policies.md) for the recommended identity and device access policies.</span></span>

## <a name="create-and-collaborate-on-content-with-microsoft-365-apps"></a><span data-ttu-id="c45fb-164">Microsoft 365 アプリを使用した、コンテンツの作成と共同作業</span><span class="sxs-lookup"><span data-stu-id="c45fb-164">Create and collaborate on content with Microsoft 365 Apps</span></span>

<span data-ttu-id="c45fb-165">Microsoft 365 アプリは、従業員がいつでもどこからでもシームレスに共同作業できる、エンタープライズ向けの生産的かつ安全な Office 環境です。</span><span class="sxs-lookup"><span data-stu-id="c45fb-165">Microsoft 365 Apps is the most productive and secure Office experience for enterprises, allowing people to work together seamlessly from anywhere, anytime.</span></span> <span data-ttu-id="c45fb-166">リモート ワーカーは、1 つのドキュメントに対して複数のユーザーと同時に共同作業したり、リアル タイムで編集や変更を確認したり、ノート PC、PC、モバイル デバイスで他のユーザーと共有編集したりできます。</span><span class="sxs-lookup"><span data-stu-id="c45fb-166">Remote workers can collaborate on a document with multiple people simultaneously, see edits and changes in real time, and coauthor with others on any laptop, PC, or mobile device.</span></span>

<span data-ttu-id="c45fb-167">詳細については、「[Microsoft 365 Apps の展開ガイド](/deployoffice/deployment-guide-microsoft-365-apps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c45fb-167">For more information, see the [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

## <a name="admin-technical-resources-for-productivity-apps-and-services"></a><span data-ttu-id="c45fb-168">生産性向上アプリとサービスに関する管理技術リソース</span><span class="sxs-lookup"><span data-stu-id="c45fb-168">Admin technical resources for productivity apps and services</span></span>

- [<span data-ttu-id="c45fb-169">Microsoft Teams を使用してリモート ワーカーをサポートする</span><span class="sxs-lookup"><span data-stu-id="c45fb-169">Support remote workers using Microsoft Teams</span></span>](/microsoftteams/support-remote-work-with-teams)
- [<span data-ttu-id="c45fb-170">Microsoft Teams Web キャストによるハイブリッド作業の有効化</span><span class="sxs-lookup"><span data-stu-id="c45fb-170">Enabling hybrid work with Microsoft Teams webcasts</span></span>](https://resources.techcommunity.microsoft.com/enabling-hybrid-work/)
- [<span data-ttu-id="c45fb-171">Teams Customer Success Kit のダウンロード</span><span class="sxs-lookup"><span data-stu-id="c45fb-171">Teams Customer Success Kit download</span></span>](https://www.microsoft.com/download/details.aspx?id=54244)
- [<span data-ttu-id="c45fb-172">導入を推進するためのツール</span><span class="sxs-lookup"><span data-stu-id="c45fb-172">Tools for driving Teams adoption</span></span>](/microsoftteams/adopt-tools-and-downloads) 
- [<span data-ttu-id="c45fb-173">Microsoft Teams の変更管理戦略を作成する</span><span class="sxs-lookup"><span data-stu-id="c45fb-173">Create a change management strategy for Microsoft Teams</span></span>](/MicrosoftTeams/change-management-strategy)
- [<span data-ttu-id="c45fb-174">3 層の保護を使ってチームを構成する</span><span class="sxs-lookup"><span data-stu-id="c45fb-174">Teams with three tiers of protection</span></span>](configure-teams-three-tiers-protection.md)

## <a name="user-training-resources-for-productivity-apps-and-services"></a><span data-ttu-id="c45fb-175">生産性向上アプリとサービスに関するユーザー トレーニング リソース</span><span class="sxs-lookup"><span data-stu-id="c45fb-175">User training resources for productivity apps and services</span></span>

- [<span data-ttu-id="c45fb-176">Office と Microsoft 365 についてユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="c45fb-176">Train your users on Office and Microsoft 365</span></span>](https://support.microsoft.com/office/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c27)
- [<span data-ttu-id="c45fb-177">Web 用 Office を使用</span><span class="sxs-lookup"><span data-stu-id="c45fb-177">Use Office for the web</span></span>](https://support.microsoft.com/office/get-started-with-office-for-the-web-in-microsoft-365-5622c7c9-721d-4b3d-8cb9-a7276c2470e5)

## <a name="next-step"></a><span data-ttu-id="c45fb-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="c45fb-178">Next step</span></span>

<span data-ttu-id="c45fb-179">[![手順 6: ユーザーを訓練し、その成功を監視する](../media/empower-people-to-work-remotely/remote-workers-step-grid-6.png)](empower-people-to-work-remotely-train-monitor-usage.md)</span><span class="sxs-lookup"><span data-stu-id="c45fb-179">[![Step 6: Train your users and monitor their success](../media/empower-people-to-work-remotely/remote-workers-step-grid-6.png)](empower-people-to-work-remotely-train-monitor-usage.md)</span></span>

<span data-ttu-id="c45fb-180">[手順 6](empower-people-to-work-remotely-train-monitor-usage.md) に進んで、ユーザーをトレーニングし、その成功を監視します。</span><span class="sxs-lookup"><span data-stu-id="c45fb-180">Continue with [Step 6](empower-people-to-work-remotely-train-monitor-usage.md) to train your users and monitor their success.</span></span>