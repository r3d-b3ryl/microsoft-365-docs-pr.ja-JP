---
title: ユーザーがデバイスを使えるようにする
description: ''
keywords: Microsoft マネージドデスクトップ、デバイス、はじめに Microsoft 365
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8f0726215c3bad5616882588360703e218bfaab4
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289449"
---
# <a name="get-your-users-ready-to-use-devices"></a><span data-ttu-id="578e7-103">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="578e7-103">Get your users ready to use devices</span></span>

<span data-ttu-id="578e7-104">Microsoft マネージドデスクトップデバイスがユーザーの手に入ってきたら、すぐに作業を開始できます。</span><span class="sxs-lookup"><span data-stu-id="578e7-104">Once a Microsoft Managed Desktop device is in the hands of your user, getting started with it is fast and easy.</span></span> <span data-ttu-id="578e7-105">デバイスには、現在のバージョンの Windows が事前に構成されており、ユーザーがセットアップを完了したときに、構成とアプリがクラウドからインストールされます。</span><span class="sxs-lookup"><span data-stu-id="578e7-105">Devices come pre-configured with the current version of Windows, and configurations and apps are installed from the cloud as the user completes setup.</span></span> 
 
<span data-ttu-id="578e7-106">これをさらに簡単にするために、最初のセットアップについて説明するガイドを提供し、必要に応じて、セットアップと後で使用するためのヘルプリソースを用意しています。</span><span class="sxs-lookup"><span data-stu-id="578e7-106">To make this even easier, we offer a guide that walks your users through the initial setup and provides help resources both for the setup and for use later, if needed.</span></span> <span data-ttu-id="578e7-107">このガイドをカスタマイズして、組織に固有の特定の詳細を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="578e7-107">You can customize this guide to include certain details specific to your organization.</span></span> <span data-ttu-id="578e7-108">その後、自分のデバイスと共に、ユーザーにガイドを直接配布します。</span><span class="sxs-lookup"><span data-stu-id="578e7-108">You then distribute the guide directly to your users along with their device.</span></span> <span data-ttu-id="578e7-109">2つのバージョンがあります。1つは Microsoft のサポートシステム (Get Help app) を使用する組織用で、もう1つはユーザーに対して別のサポートを提供するものです。</span><span class="sxs-lookup"><span data-stu-id="578e7-109">There are two versions, one for organizations using Microsoft's support system (the Get Help app), one for those providing alternative support for their users.</span></span>

## <a name="to-prepare-the-guide"></a><span data-ttu-id="578e7-110">ガイドを準備するには</span><span class="sxs-lookup"><span data-stu-id="578e7-110">To prepare the guide</span></span>

1. <span data-ttu-id="578e7-111">組織に適したバージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="578e7-111">Download the version appropriate to your organization:</span></span>
- <span data-ttu-id="578e7-112">[Microsoft マネージドデスクトップ-デバイスの使用を開始する (ヘルプバージョンを取得する)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/microsoft-managed-desktop-user-guide-help-custom-v3.pdf) -ユーザーが Microsoft のサポートシステムを使用する場合は、このバージョンを使用してください。</span><span class="sxs-lookup"><span data-stu-id="578e7-112">[Microsoft Managed Desktop - Get started with your device (Get Help version)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/microsoft-managed-desktop-user-guide-help-custom-v3.pdf) - use this version if your users will use Microsoft's support system.</span></span>
- <span data-ttu-id="578e7-113">[Microsoft マネージドデスクトップ-デバイスで](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/microsoft-managed-desktop-user-guide-no-help-custom-v2.pdf) の使用を開始する-ユーザーが Microsoft のサポートシステムを使用し *ない* 場合は、このバージョンを使用してください。</span><span class="sxs-lookup"><span data-stu-id="578e7-113">[Microsoft Managed Desktop - Get started with your device](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/microsoft-managed-desktop-user-guide-no-help-custom-v2.pdf) - use this version if your users will *not* use Microsoft's support system.</span></span>
2. <span data-ttu-id="578e7-114">PDF ファイルを開くことができる任意のアプリを使用して、組織に関連する詳細情報を記入します。</span><span class="sxs-lookup"><span data-stu-id="578e7-114">Use any app capable of opening PDF files to fill in details relevant to your organization:</span></span>
    - <span data-ttu-id="578e7-115">セットアップを続行するためにユーザーが接続する必要のあるネットワークの名前 (ガイドの手順 3)</span><span class="sxs-lookup"><span data-stu-id="578e7-115">The name of the network your users should connect to in order to continue setup (Step 3 in the guide)</span></span>
    - <span data-ttu-id="578e7-116">組織の Azure テナントアカウントの名前 (ガイドの手順 4)</span><span class="sxs-lookup"><span data-stu-id="578e7-116">The name of your organization's Azure tenant account (Step 4 in the guide)</span></span>
    - <span data-ttu-id="578e7-117">組織の内部 IT サポートの連絡先情報 (2 ページ目の上部)</span><span class="sxs-lookup"><span data-stu-id="578e7-117">Contact information for your organization's internal IT support (top of second page)</span></span>
3. <span data-ttu-id="578e7-118">編集した PDF を保存し、ユーザーに配布します。</span><span class="sxs-lookup"><span data-stu-id="578e7-118">Save the edited PDF, and then distribute to your users.</span></span> 

## <a name="ready-to-use-guide"></a><span data-ttu-id="578e7-119">「すぐに使用できるガイド」</span><span class="sxs-lookup"><span data-stu-id="578e7-119">"Ready-to-use guide"</span></span>

<span data-ttu-id="578e7-120">また、カスタマイズする必要がない組織に対して、より一般的なバージョンのガイドを提供しています。</span><span class="sxs-lookup"><span data-stu-id="578e7-120">We also provide a more generic version of the guide for those organizations that don't need to customize it.</span></span> <span data-ttu-id="578e7-121">2つのバージョンがあります。1つは Microsoft のサポートシステム (Get Help app) を使用する組織用で、もう1つはユーザーに対して別のサポートを提供するものです。</span><span class="sxs-lookup"><span data-stu-id="578e7-121">There are two versions, one for organizations using Microsoft's support system (the Get Help app), one for those providing alternative support for their users.</span></span> 

- <span data-ttu-id="578e7-122">[Microsoft マネージドデスクトップ-デバイスの使用を開始します (ヘルプバージョンの準備ができ](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/microsoft-managed-desktop-user-guide-help-v3.pdf) ています)。ユーザーが Microsoft のサポートシステムを使用する場合は、このバージョンをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="578e7-122">[Microsoft Managed Desktop - Get started with your device (Get Help version - ready to use)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/microsoft-managed-desktop-user-guide-help-v3.pdf) - use this version if your users will use Microsoft's support system.</span></span>
- <span data-ttu-id="578e7-123">[Microsoft マネージドデスクトップ-デバイスの使用を開始します (使用可能な状態)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/microsoft-managed-desktop-user-guide-no-help-v2.pdf) 。ユーザーが Microsoft のサポートシステムを使用し *ない* 場合は、このバージョンを使用してください。</span><span class="sxs-lookup"><span data-stu-id="578e7-123">[Microsoft Managed Desktop - Get started with your device (ready to use)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/microsoft-managed-desktop-user-guide-no-help-v2.pdf) - use this version if your users will *not* use Microsoft's support system.</span></span>

<span data-ttu-id="578e7-124">この時点で、アプリの展開に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="578e7-124">At this point, you're ready to move on to deploying apps:</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="578e7-125">Microsoft マネージドデスクトップの使用を開始する手順</span><span class="sxs-lookup"><span data-stu-id="578e7-125">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="578e7-126">管理ポータルで管理者の連絡先を追加および確認する</span><span class="sxs-lookup"><span data-stu-id="578e7-126">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="578e7-127">条件付きアクセスを調整する</span><span class="sxs-lookup"><span data-stu-id="578e7-127">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="578e7-128">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="578e7-128">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="578e7-129">Intune 会社ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="578e7-129">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="578e7-130">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="578e7-130">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="578e7-131">デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="578e7-131">Set up devices</span></span>](set-up-devices.md)
7. <span data-ttu-id="578e7-132">デバイスを使用できるようにユーザーを取得する (このトピック)</span><span class="sxs-lookup"><span data-stu-id="578e7-132">Get your users ready to use devices (this topic)</span></span>
8. [<span data-ttu-id="578e7-133">アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="578e7-133">Deploy apps</span></span>](deploy-apps.md)
