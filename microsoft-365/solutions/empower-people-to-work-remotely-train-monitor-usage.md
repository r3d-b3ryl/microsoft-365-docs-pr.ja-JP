---
title: 'ステップ 6: リモートワーカーをトレーニングし、使用状況のフィードバックに対処する'
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
description: ユーザーをトレーニングして、問題にすばやく対処できるようにします。
ms.openlocfilehash: 662b0d6d7a40a69b3e5c10f3aeea63c2e5237d6d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916168"
---
# <a name="step-6-train-remote-workers-and-address-usage-feedback"></a><span data-ttu-id="deaab-103">ステップ 6: リモートワーカーをトレーニングし、使用状況のフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="deaab-103">Step 6: Train remote workers and address usage feedback</span></span>

<span data-ttu-id="deaab-104">リモート ワーカーを以下の内容についてトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="deaab-104">Train your remote workers on:</span></span>

- <span data-ttu-id="deaab-105">MFA を使用して、追加の検証方法を登録するなど、正しいサインインの手順。</span><span class="sxs-lookup"><span data-stu-id="deaab-105">Proper sign-in procedures using MFA, including registering an additional verification method.</span></span>
- <span data-ttu-id="deaab-106">デバイスの使用と、エンドポイント管理ポリシーを使用して非準拠または管理されていないデバイスのアクセスをブロックする方法。</span><span class="sxs-lookup"><span data-stu-id="deaab-106">The use of devices and how endpoint management policies can be used to block access for non-compliant or unmanaged devices.</span></span>
- <span data-ttu-id="deaab-107">許可されたアプリの使用と、エンドポイント管理アプリケーション ポリシーを使用していくつかのアプリの使用をブロックする方法。</span><span class="sxs-lookup"><span data-stu-id="deaab-107">The use of allowed apps and how endpoint management application polices can be used to block the use of some apps.</span></span>
- <span data-ttu-id="deaab-108">Windows 10 Enterprise のセキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="deaab-108">Windows 10 Enterprise security features.</span></span>
- <span data-ttu-id="deaab-109">[Teams](/microsoftteams/training-microsoft-teams-landing-page) を使用してチャット、ビデオベースの会議、ドキュメント共有、およびスレッド形式の会話を行う方法。</span><span class="sxs-lookup"><span data-stu-id="deaab-109">How to use [Teams](/microsoftteams/training-microsoft-teams-landing-page) for chat, video-based conferencing, document sharing, and threaded conversations.</span></span>
- <span data-ttu-id="deaab-110">メールとスケジュール設定に [Outlook](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) を使用する方法。</span><span class="sxs-lookup"><span data-stu-id="deaab-110">How to use [Outlook](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) for email and scheduling.</span></span>
- <span data-ttu-id="deaab-111">[SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) チームまたはコミュニケーション サイトと [OneDrive](https://support.office.com/article/onedrive-video-training-1f608184-b7e6-43ca-8753-2ff679203132) フォルダーを使用して、ユーザーのライブラリおよびグループに属するファイルを閲覧および共同作業する方法。</span><span class="sxs-lookup"><span data-stu-id="deaab-111">How to use [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) team or communication sites and [OneDrive](https://support.office.com/article/onedrive-video-training-1f608184-b7e6-43ca-8753-2ff679203132) folders to browse and collaborate on files in a user's library and those belonging to a group.</span></span>

<span data-ttu-id="deaab-112">このトレーニングには、従業員が上記の機能とその結果を体感できるように、実践的な演習を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="deaab-112">This training should include hands-on exercises so that your workers can experience these capabilities and their results.</span></span>

<span data-ttu-id="deaab-113">チームや Yammer グループなど、リモート ワーカーが質問したり、問題に対処したりするためのフォーラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="deaab-113">Create a forum for your remote workers to ask questions or get issues addressed, such as a team or a Yammer group.</span></span>

<span data-ttu-id="deaab-114">トレーニング後の数週間、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="deaab-114">In the weeks after training:</span></span>

- <span data-ttu-id="deaab-115">フォーラムでリモート ワーカーのフィードバックにすばやく対処し、必要に応じてリモート ワーカーのポリシーと構成を調整します。</span><span class="sxs-lookup"><span data-stu-id="deaab-115">Quickly address remote worker feedback in your forum and adjust your remote worker policies and configurations as needed.</span></span>
- <span data-ttu-id="deaab-116">Teams、メール、SharePoint サイト、および OneDrive フォルダーの使用状況を分析し、ユーザーによる導入に対する期待と比較します。</span><span class="sxs-lookup"><span data-stu-id="deaab-116">Analyze usage for teams, email, SharePoint sites, and OneDrive folders and compare it with your expectations of user adoption.</span></span>

<span data-ttu-id="deaab-117">それから、必要に応じてユーザーの再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="deaab-117">Then, retrain your users as needed.</span></span>

## <a name="results-of-step-6"></a><span data-ttu-id="deaab-118">ステップ 6 の結果</span><span class="sxs-lookup"><span data-stu-id="deaab-118">Results of Step 6</span></span>

<span data-ttu-id="deaab-119">リモート ワーカーはトレーニングを受けており、また、リモート アクセスおよび生産性のアプリについてフィードバックを提供したり、問題に応答するオープンフォーラムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="deaab-119">Your remote workers are trained and there is a responsive and open forum for them to provide feedback and post issues with remote access and productivity apps.</span></span>