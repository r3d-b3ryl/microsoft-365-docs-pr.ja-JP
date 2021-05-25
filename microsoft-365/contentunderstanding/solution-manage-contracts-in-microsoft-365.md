---
title: ソリューションを使用して契約Microsoft 365する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Syntex、Microsoft 365 リスト、SharePoint、SharePoint Microsoft Teams、およびPower Automateのソリューションを使用して契約を管理する方法についてPower Automate。
ms.openlocfilehash: 219ab13eb5787bef566ede0c5dc856da29d96837
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651286"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a><span data-ttu-id="5073e-103">ソリューションを使用して契約Microsoft 365する</span><span class="sxs-lookup"><span data-stu-id="5073e-103">Manage contracts using a Microsoft 365 solution</span></span>

<span data-ttu-id="5073e-104">この記事では、Syntex と組織のコンポーネントを使用して、組織の契約管理SharePointする方法についてMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="5073e-104">This article describes how to create a contracts management solution for your organization by using SharePoint Syntex and components of Microsoft 365.</span></span> <span data-ttu-id="5073e-105">独自のビジネス ニーズに合ったソリューションの計画と作成に役立つフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="5073e-105">It provides you with a framework to help you plan and create a solution that fits your unique business needs.</span></span> <span data-ttu-id="5073e-106">このソリューションがビジネス ニーズ全体に合わない場合でも、カスタム契約管理ソリューションを作成する計画で、その一部を採用できます。</span><span class="sxs-lookup"><span data-stu-id="5073e-106">Even if this solution doesn't suit your business needs as a whole, parts of it can be adopted in your planning to create a custom contract management solution.</span></span>

<span data-ttu-id="5073e-107">*このコンテンツ セットは、Microsoft 365モダン ワーク ソリューション戦略チームと一緒に、Thomas Molbach が開発したソリューションを文書化しています。*</span><span class="sxs-lookup"><span data-stu-id="5073e-107">*This content set documents a Microsoft 365 solution developed by Thomas Molbach with the Modern Work Solution Strategy Team at Microsoft.*</span></span>

## <a name="identify-the-business-problem"></a><span data-ttu-id="5073e-108">ビジネス上の問題を特定する</span><span class="sxs-lookup"><span data-stu-id="5073e-108">Identify the business problem</span></span>

<span data-ttu-id="5073e-109">契約管理システムを計画する最初の手順は、解決しようとしている問題を理解する方法です。</span><span class="sxs-lookup"><span data-stu-id="5073e-109">The first step in planning your contract management system is to understand the problem you're trying to solve.</span></span> <span data-ttu-id="5073e-110">このソリューションでは、次の 4 つの重要な問題に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5073e-110">For this solution, four key issues need to be addressed:</span></span>

- <span data-ttu-id="5073e-111">**コントラクトを識別します**。</span><span class="sxs-lookup"><span data-stu-id="5073e-111">**Identify contracts**.</span></span> <span data-ttu-id="5073e-112">組織は、請求書、契約、作業明細書など、多くのドキュメントを処理します。</span><span class="sxs-lookup"><span data-stu-id="5073e-112">Your organization works with many documents, such as invoices, contracts, statements of work, and so on.</span></span>  <span data-ttu-id="5073e-113">電子メールで送信されるデジタルアセットと、従来のメールを介して送信される紙のアセットがあります。</span><span class="sxs-lookup"><span data-stu-id="5073e-113">Some are digital assets sent through email, and some are paper assets sent through traditional mail.</span></span> <span data-ttu-id="5073e-114">他のすべてのドキュメントからすべての顧客契約を識別し、それらを分類する方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="5073e-114">You need a way to identify all customer contracts from all other documents, and then classifying them as such.</span></span>

- <span data-ttu-id="5073e-115">**契約承認の履歴を追跡します**。</span><span class="sxs-lookup"><span data-stu-id="5073e-115">**Track the history of contract approvals**.</span></span> <span data-ttu-id="5073e-116">組織では、契約が承認または却下されたかどうか、および支払いが処理されたかどうかを確認するための信頼性の高い方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="5073e-116">Your organization needs a reliable way to find whether contracts have been either approved or rejected, and whether payment has been processed.</span></span> 

- <span data-ttu-id="5073e-117">**契約の承認を管理するサイト**。</span><span class="sxs-lookup"><span data-stu-id="5073e-117">**Site to manage contract approvals**.</span></span> <span data-ttu-id="5073e-118">組織では、必要なすべての関係者が契約を簡単に確認できる共同作業サイトをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5073e-118">Your organization needs to set up a collaborative site in which all required stakeholders can easily review contracts.</span></span> <span data-ttu-id="5073e-119">利害関係者は、必要に応じて契約全体を確認できる必要がありますが、主に各契約の主要なフィールド (顧客名、PO 番号、総コストなど) を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5073e-119">Stakeholders should be able to review the whole contract if needed, but mostly care about seeing several key fields from each contract (for example, customer name, PO number, and total cost).</span></span> <span data-ttu-id="5073e-120">関係者は、受信した契約を簡単に承認または拒否できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5073e-120">Stakeholders should be able to easily approve or reject incoming contracts.</span></span>

- <span data-ttu-id="5073e-121">**レビューされた契約をルーティングします**。</span><span class="sxs-lookup"><span data-stu-id="5073e-121">**Route reviewed contracts**.</span></span> <span data-ttu-id="5073e-122">承認済みおよび却下された契約は、特定のワークフローを通じてルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5073e-122">Approved and rejected contracts need to be routed through a specific workflow.</span></span> <span data-ttu-id="5073e-123">承認された契約は、支払い処理のためにサードパーティアプリケーションにルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5073e-123">Approved contracts need to be routed to a third-party application for payment processing.</span></span> <span data-ttu-id="5073e-124">拒否された契約は、追加のレビューのためにルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5073e-124">Rejected contracts need to be routed for additional review.</span></span>

## <a name="overview-of-the-solution"></a><span data-ttu-id="5073e-125">ソリューションの概要</span><span class="sxs-lookup"><span data-stu-id="5073e-125">Overview of the solution</span></span>

  ![Syntex、SharePointリストSharePoint、Teams、およびPower Automate。](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

<span data-ttu-id="5073e-127">この契約管理ソリューション のガイダンスには、次の 4 つのコンポーネントMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="5073e-127">This contract management solution guidance includes four components of Microsoft 365:</span></span>

- <span data-ttu-id="5073e-128">**Microsoft SharePoint Syntex**: コントラクト ファイルを識別して分類し、そこから適切なデータを抽出するモデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5073e-128">**Microsoft SharePoint Syntex**: Create models to identify and classify your contract files and then extract the appropriate data from them.</span></span>

- <span data-ttu-id="5073e-129">**Microsoft SharePointリスト**: モダン リストで使用できる書式を使用SharePointビジネスに優しい形式で契約を提示します。</span><span class="sxs-lookup"><span data-stu-id="5073e-129">**Microsoft SharePoint lists**: Use the formatting available in modern SharePoint lists to present contracts in a business-friendly format.</span></span>

- <span data-ttu-id="5073e-130">**Microsoft Teams**: 関係者が契約を確認および管理Teams、チャネルと関連付けられたタブの機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="5073e-130">**Microsoft Teams**: Use the functionality of a Teams channel and associated tabs to allow your stakeholders to review and manage contracts.</span></span>

- <span data-ttu-id="5073e-131">**Power Automate:** フローを使用して、承認プロセスを通じて契約をガイドし、その後、支払いのためにサードパーティ製のアプリケーションに案内します。</span><span class="sxs-lookup"><span data-stu-id="5073e-131">**Power Automate**: Use flows to guide contracts through the approval process, and then to a third-party application for payment.</span></span>

### <a name="how-it-all-works"></a><span data-ttu-id="5073e-132">すべての動作方法</span><span class="sxs-lookup"><span data-stu-id="5073e-132">How it all works</span></span>

  ![ドキュメントのアップロード、データの抽出、関係者への通知、契約の承認または却下を行うワークフローを示すソリューションの図。](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. <span data-ttu-id="5073e-134">ドキュメントは、ドキュメント ライブラリSharePointアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="5073e-134">Documents are uploaded to a SharePoint document library.</span></span> <span data-ttu-id="5073e-135">Syntex SharePoint理解モデルがドキュメント ライブラリに適用されています。</span><span class="sxs-lookup"><span data-stu-id="5073e-135">A SharePoint Syntex document understanding model has been applied to the document library.</span></span> <span data-ttu-id="5073e-136">各ファイルをチェックして、探すトレーニングを受けた "コントラクト" コンテンツ タイプと一致するコンテンツ タイプが一致する場合を確認します。</span><span class="sxs-lookup"><span data-stu-id="5073e-136">It checks each file to see if any match a "contract" content type it's trained to look for.</span></span> <span data-ttu-id="5073e-137">一致が見つかった場合は、ファイルを "コントラクト" として分類し、ドキュメントのコンテンツ タイプを更新します。</span><span class="sxs-lookup"><span data-stu-id="5073e-137">If it finds a match, it classifies the file as a "contract" and updates the content type for the document.</span></span>

2. <span data-ttu-id="5073e-138">また、このモデルは、関係者が関心を持つ各契約ファイル (クライアント、請負業者、手数料の金額など) から特定のデータを *引き出します*。</span><span class="sxs-lookup"><span data-stu-id="5073e-138">The model also pulls out specific data from each contract file that stakeholders are interested in seeing, such as the *Client*, *Contractor*, and *Fee amount*.</span></span>

    <span data-ttu-id="5073e-139">次のページは、モデルが識別するためにトレーニングされる契約の例です。</span><span class="sxs-lookup"><span data-stu-id="5073e-139">The following page is an example of a contract that the model is trained to identify.</span></span>

      ![コントラクトの例。](../media/content-understanding/contract.png)

3. <span data-ttu-id="5073e-141">このMicrosoft Teams、すべての関係者は、ドキュメント ライブラリ内Teams承認または却下のために表示されるセキュリティで保護されたチャネルのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="5073e-141">In Microsoft Teams, all stakeholders are members of a secure Teams channel in which all contracts in the document library are visible for approval or rejection.</span></span> <span data-ttu-id="5073e-142">新しいTeamsを使用すると、すべての関係者に新しい契約を確認する必要があるときに通知されます。</span><span class="sxs-lookup"><span data-stu-id="5073e-142">By using Teams functionality, all stakeholders are notified when new contracts need to be reviewed.</span></span>
 
4. <span data-ttu-id="5073e-143">契約を使用Power Automate、契約は、契約チャネルの承認プロセスをTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="5073e-143">By using Power Automate, contracts are moved through the approval process in the Teams channel.</span></span> <span data-ttu-id="5073e-144">メンバーが契約を承認すると、契約の状態が承認に変更され、すべてのメンバーに Teams 投稿を通じて通知され、契約が支払いの準備ができていることを示す行アイテムが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5073e-144">When a member approves a contract, the contract status is changed to approve, all members are notified through a Teams post, and a line item is created to show that the contract is ready for payout.</span></span> <span data-ttu-id="5073e-145">このプロセスは、支払いのためにサードパーティの金融アプリケーションに直接書き込むまで拡張できます。</span><span class="sxs-lookup"><span data-stu-id="5073e-145">This process can be extended to write directly to a third-party financial application for payment.</span></span>

5.  <span data-ttu-id="5073e-146">メンバーが契約を拒否すると、ステータスが拒否に変更され、すべてのメンバーに通知が投稿Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="5073e-146">When a member rejects a contract, the status is changed to rejected, and all members are notified through a Teams post.</span></span>

6. <span data-ttu-id="5073e-147">このソリューションの最後の結果は、組織の自動化されたビジネス プロセスです。</span><span class="sxs-lookup"><span data-stu-id="5073e-147">The end result of this solution is an automated business process for your organization.</span></span> <span data-ttu-id="5073e-148">従業員は、ドキュメントの承認ワークフローを開始Teamsカスタム タイル ビューを簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5073e-148">Employees can easily use the custom tile view in Teams to initiate and monitor the approval workflow of your documents.</span></span> 

     ![[契約] タブ。](../media/content-understanding/tile-view.png)

## <a name="create-the-solution"></a><span data-ttu-id="5073e-150">ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="5073e-150">Create the solution</span></span>

<span data-ttu-id="5073e-151">次のセクションでは、契約管理ソリューションを構成する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="5073e-151">The next sections will go into detail about how to configure your contracts management solution.</span></span> <span data-ttu-id="5073e-152">次の 3 つの手順に分かれています。</span><span class="sxs-lookup"><span data-stu-id="5073e-152">It's divided into three steps:</span></span>

- [<span data-ttu-id="5073e-153">手順 1.Syntex SharePointを使用してコントラクト ファイルを識別し、データを抽出する</span><span class="sxs-lookup"><span data-stu-id="5073e-153">Step 1. Use SharePoint Syntex to identify contract files and extract data</span></span>](solution-manage-contracts-step1.md)
- [<span data-ttu-id="5073e-154">手順 2.契約Microsoft Teamsチャネルを作成するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="5073e-154">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
- [<span data-ttu-id="5073e-155">手順 3.契約Power Automate処理するフローを作成するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="5073e-155">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
