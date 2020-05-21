---
title: 'ステップ 6: リモートワーカーをトレーニングし、使用状況のフィードバックに対処する'
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
- M365solutions
ms.custom: ''
description: ユーザーをトレーニングして、問題にすばやく対処できるようにします。
ms.openlocfilehash: bb8c6614ed383136ef5724d45637891ee978c9cd
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160728"
---
# <a name="step-6-train-remote-workers-and-address-usage-feedback"></a><span data-ttu-id="b121c-103">ステップ 6: リモートワーカーをトレーニングし、使用状況のフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="b121c-103">Step 6: Train remote workers and address usage feedback</span></span>

<span data-ttu-id="b121c-104">リモート ワーカーを以下の内容についてトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="b121c-104">Train your remote workers on:</span></span>

- <span data-ttu-id="b121c-105">MFA を使用して、追加の検証方法を登録するなど、正しいサインインの手順。</span><span class="sxs-lookup"><span data-stu-id="b121c-105">Proper sign-in procedures using MFA, including registering an additional verification method.</span></span>
- <span data-ttu-id="b121c-106">デバイスの使用と、エンドポイント管理ポリシーを使用して非準拠デバイスのアクセスをブロックする方法。</span><span class="sxs-lookup"><span data-stu-id="b121c-106">The use of devices and how endpoint management policies can be used to block access for non-compliant devices.</span></span>
- <span data-ttu-id="b121c-107">許可されたアプリの使用と、エンドポイント管理アプリ ポリシーを使用してアプリの使用をブロックする方法。</span><span class="sxs-lookup"><span data-stu-id="b121c-107">The use of allowed apps and how endpoint management app polices can be used to block the use of apps.</span></span>
- <span data-ttu-id="b121c-108">Windows 10 Enterprise のセキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="b121c-108">Windows 10 Enterprise security features.</span></span>
- <span data-ttu-id="b121c-109">[Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) を使用してチャット、ビデオベースの会議、ドキュメント共有、およびスレッド形式の会話を行う方法。</span><span class="sxs-lookup"><span data-stu-id="b121c-109">How to use [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) for chat, video-based conferencing, document sharing, and threaded conversations.</span></span>
- <span data-ttu-id="b121c-110">メールとスケジュール設定に [Outlook](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) を使用する方法。</span><span class="sxs-lookup"><span data-stu-id="b121c-110">How to use [Outlook](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) for email and scheduling.</span></span>
- <span data-ttu-id="b121c-111">[SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) チームまたはコミュニケーション サイトと [OneDrive](https://support.office.com/article/onedrive-video-training-1f608184-b7e6-43ca-8753-2ff679203132) フォルダーを使用して、ユーザーのライブラリおよびグループに属するファイルを閲覧および共同作業する方法。</span><span class="sxs-lookup"><span data-stu-id="b121c-111">How to use [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) team or communication sites and [OneDrive](https://support.office.com/article/onedrive-video-training-1f608184-b7e6-43ca-8753-2ff679203132) folders to browse and collaborate on files in a user's library and those belonging to a group.</span></span>

<span data-ttu-id="b121c-112">このトレーニングには、従業員が上記の機能とその結果を体感できるように、実践的な演習を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b121c-112">This training should include hands-on exercises so that your workers can experience these capabilities and their results.</span></span>

<span data-ttu-id="b121c-113">トレーニング後の数週間、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="b121c-113">In the weeks after training:</span></span>

- <span data-ttu-id="b121c-114">リモート ワーカーのフィードバックに迅速に対応し、ポリシーと構成を微調整します。</span><span class="sxs-lookup"><span data-stu-id="b121c-114">Quickly address remote worker feedback and fine tune policies and configurations.</span></span>
- <span data-ttu-id="b121c-115">Teams、メール、SharePoint サイト、および OneDrive フォルダーの使用状況を分析し、予想される使用状況と比較します。</span><span class="sxs-lookup"><span data-stu-id="b121c-115">Analyze usage for teams, email, SharePoint sites, and OneDrive folders and compare it with usage expectations.</span></span>

<span data-ttu-id="b121c-116">必要に応じて、ユーザーの再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="b121c-116">Retrain your users as needed.</span></span>

## <a name="results-of-step-6"></a><span data-ttu-id="b121c-117">ステップ 6 の結果</span><span class="sxs-lookup"><span data-stu-id="b121c-117">Results of Step 6</span></span>

<span data-ttu-id="b121c-118">リモートワーカーはトレーニングを受けており、また、リモートアクセスおよび生産性のアプリやサービスについてフィードバックを提供したり、問題に応答するオープンフォーラムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b121c-118">Your remote workers are trained and there is a responsive and open forum for them to provide feedback and post issues with remote access and productivity apps and services.</span></span>

