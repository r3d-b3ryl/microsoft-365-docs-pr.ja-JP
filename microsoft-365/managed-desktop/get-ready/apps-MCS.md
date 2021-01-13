---
title: Microsoft コンサルティング サービスを使用する
description: MCS を使用してアプリをパッケージ化するための準備と手順
keywords: Microsoft マネージド デスクトップ, Microsoft 365, サービス, ドキュメント, アプリ, MCS, パッケージ化
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841425"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="92aa7-104">Microsoft コンサルティング サービスを使用する</span><span class="sxs-lookup"><span data-stu-id="92aa7-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="92aa7-105">Microsoft Consulting Services (MCS) と関わり、Microsoft マネージド デスクトップで使用するためにアプリをパッケージ化できます。</span><span class="sxs-lookup"><span data-stu-id="92aa7-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="92aa7-106">詳細については、アカウント担当者と連絡を取り、MCS に連絡し、特定のアプリ パッケージ プロジェクトの範囲を設定します。</span><span class="sxs-lookup"><span data-stu-id="92aa7-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="92aa7-107">役割と責任</span><span class="sxs-lookup"><span data-stu-id="92aa7-107">Roles and responsibilities</span></span>

<span data-ttu-id="92aa7-108">MCS アプリパッケージを使用するには、次 **の要素を指定する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="92aa7-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="92aa7-109">ソース インストーラー ファイル (たとえば、setup.exe .msi)。</span><span class="sxs-lookup"><span data-stu-id="92aa7-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="92aa7-110">インストール手順。最終的なインストールの外観に関する詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="92aa7-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="92aa7-111">たとえば、アプリへのデスクトップ ショートカットが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="92aa7-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="92aa7-112">アプリの可視性を確認する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="92aa7-112">What should the app's visibility be?</span></span> <span data-ttu-id="92aa7-113">アプリはサーバーに接続する必要があります。接続されている場合は、どちらですか。</span><span class="sxs-lookup"><span data-stu-id="92aa7-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="92aa7-114">詳細については、アプリケーション パッケージ [要求テンプレートを参照してください](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。</span><span class="sxs-lookup"><span data-stu-id="92aa7-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="92aa7-115">独自の受け入れテストを実行して、アプリが環境内で必要な動作を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92aa7-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="92aa7-116">**MCS は、次の処理を行います。**</span><span class="sxs-lookup"><span data-stu-id="92aa7-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="92aa7-117">Microsoft マネージド デスクトップ環境でアプリが禁止または制限されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="92aa7-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="92aa7-118">Windows 10 との互換性を確保するためのアプリのインストール、開始、アンインストールのテスト。</span><span class="sxs-lookup"><span data-stu-id="92aa7-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="92aa7-119">MCS が互換性の問題を検出すると、修復のために Desktop App [Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) プログラムにアプリを渡します。</span><span class="sxs-lookup"><span data-stu-id="92aa7-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="92aa7-120">アプリを仕様にパッケージ化し、Microsoft Intune を使用してアプリの展開をテストします。</span><span class="sxs-lookup"><span data-stu-id="92aa7-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="92aa7-121">アプリの配信スケジュール</span><span class="sxs-lookup"><span data-stu-id="92aa7-121">App delivery schedule</span></span>

<span data-ttu-id="92aa7-122">アプリ情報を Microsoft マネージド デスクトップ ポータルにアップロードして、パッケージ化プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="92aa7-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="92aa7-123">パッケージ チームは、毎週木曜日に新しい提出をレビューします。</span><span class="sxs-lookup"><span data-stu-id="92aa7-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="92aa7-124">レビューとパッケージ化の後、パッケージ アプリは次の金曜日に配信されます。</span><span class="sxs-lookup"><span data-stu-id="92aa7-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="92aa7-125">1 週間に最大 5 つのアプリをパッケージ化して開始できますが、サービスはニーズに合わせて拡大できます。</span><span class="sxs-lookup"><span data-stu-id="92aa7-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![木曜日 (この例では 21 日)、翌日のメディア検証、次の月曜日 (25 日) のパッケージ化、後続の金曜日 (29 日) のアプリ配信を示すカレンダー](../../media/MCS-cal.png)

<span data-ttu-id="92aa7-127">アプリが配信された後に通知されます。</span><span class="sxs-lookup"><span data-stu-id="92aa7-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="92aa7-128">その時点で、Microsoft マネージド デスクトップ ポータルで承認テストを実行し、作業を承認するには 21 日間があります。</span><span class="sxs-lookup"><span data-stu-id="92aa7-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="92aa7-129">受け入れテスト中にアプリに関する問題を発見した場合は、Microsoft マネージド デスクトップ ポータルでアプリを拒否すると、MCS パッケージーとメールで接続し、問題を理解して解決します。</span><span class="sxs-lookup"><span data-stu-id="92aa7-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="92aa7-130">アカウントと環境のテスト</span><span class="sxs-lookup"><span data-stu-id="92aa7-130">Testing accounts and environment</span></span>

<span data-ttu-id="92aa7-131">パッケージ チームが Microsoft Intune への移行を完了するには、特定のアクセス許可を提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92aa7-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="92aa7-132">アプリを追加して割り当てるパッケージ化者向け Microsoft Intune のアプリ展開機能へのアクセス</span><span class="sxs-lookup"><span data-stu-id="92aa7-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="92aa7-133">アプリをテストできるパッケージのグループ、ユーザー アカウント、ライセンスをテストする</span><span class="sxs-lookup"><span data-stu-id="92aa7-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="92aa7-134">MCS は、これらのアクセス許可を使用して次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="92aa7-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="92aa7-135">Microsoft マネージド デスクトップ用に構成された仮想マシンでアプリが動作するようにする</span><span class="sxs-lookup"><span data-stu-id="92aa7-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="92aa7-136">ユーザーへの展開のためにアプリを Microsoft Intune にアップロードする</span><span class="sxs-lookup"><span data-stu-id="92aa7-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="92aa7-137">これらのアクセス許可がない場合、MCS は先に進む可能性がありますが、アプリケーションを環境にアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="92aa7-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


