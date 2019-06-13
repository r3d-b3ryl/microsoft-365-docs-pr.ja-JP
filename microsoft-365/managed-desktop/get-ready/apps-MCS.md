---
title: Microsoft コンサルティングサービスを使用する
description: アプリケーションをパッケージ化するために MCS と連携するための準備と手順
keywords: Microsoft マネージドデスクトップ、Microsoft 365、service、ドキュメント、アプリ、MCS、パッケージ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 39a5102d045d9ed79b631a3b477bd1c72dea76de
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "34918732"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="3e3e7-104">Microsoft コンサルティングサービスを使用する</span><span class="sxs-lookup"><span data-stu-id="3e3e7-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="3e3e7-105">Microsoft コンサルティングサービス (MCS) と協力して、Microsoft マネージドデスクトップで使用するためにアプリをパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="3e3e7-106">詳細については、アカウント担当者と連携して MCS と連絡をとって、特定のアプリパッケージプロジェクトの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="3e3e7-107">役割と責任</span><span class="sxs-lookup"><span data-stu-id="3e3e7-107">Roles and responsibilities</span></span>

<span data-ttu-id="3e3e7-108">MCS アプリパッケージを使用するには、**次の要素を提供する必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="3e3e7-109">ソースインストーラファイル (例: setup.exe または .msi)。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="3e3e7-110">インストール手順で、最終的なインストール方法の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="3e3e7-111">たとえば、アプリにデスクトップショートカットがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="3e3e7-112">アプリの可視性をどのようにする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="3e3e7-112">What should the app's visibility be?</span></span> <span data-ttu-id="3e3e7-113">アプリをサーバーに接続し、その場合はどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-113">Should the app connect to a server and if so, which one?</span></span> <!--For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx). -->
- <span data-ttu-id="3e3e7-114">アプリが環境内で必要なときに動作することを確認するために、独自の受け入れテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-114">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="3e3e7-115">**MCS は、次の操作を行います。**</span><span class="sxs-lookup"><span data-stu-id="3e3e7-115">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="3e3e7-116">Microsoft マネージドデスクトップ環境でアプリが禁止または制限されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-116">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="3e3e7-117">Windows 10 との互換性を確保するために、アプリのインストール、開始、アンインストールをテストします。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-117">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="3e3e7-118">MCS が互換性の問題を検出した場合は、アプリを[デスクトップアプリ](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure)に渡して、修復のためのプログラムを確実に実行します。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-118">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="3e3e7-119">アプリを仕様にパッケージ化し、Microsoft Intune を使用してアプリの展開をテストします。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-119">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="3e3e7-120">アプリの配信スケジュール</span><span class="sxs-lookup"><span data-stu-id="3e3e7-120">App delivery schedule</span></span>

<span data-ttu-id="3e3e7-121">アプリの情報を Microsoft マネージドデスクトップポータルにアップロードして、パッケージ化プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-121">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="3e3e7-122">パッケージチームは、毎週木曜日に新しい提出をレビューします。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-122">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="3e3e7-123">レビューとパッケージ化後、パッケージ化されたアプリは次の金曜日に配信されます。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-123">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="3e3e7-124">1週間に最大5つのアプリを開始するためのパッケージを作成できますが、サービスはニーズに合わせて拡張できます。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-124">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![アプリのレビュー、パッケージ、および配信日を示すカレンダー](images/MCS-cal.png)

<span data-ttu-id="3e3e7-126">アプリが配信されると、通知されます。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-126">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="3e3e7-127">その時点で、承認テストを実行し、Microsoft マネージドデスクトップポータルで作業を行うことができるのは、21日です。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-127">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="3e3e7-128">受け入れテストの間にアプリに関して何らかの問題が見つかった場合は、Microsoft マネージドデスクトップポータルでアプリを拒否すると、問題を把握して解決するために、メールで MCS パッケージャーに接続されます。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-128">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="3e3e7-129">アカウントと環境のテスト</span><span class="sxs-lookup"><span data-stu-id="3e3e7-129">Testing accounts and environment</span></span>

<span data-ttu-id="3e3e7-130">パッケージ化チームが Microsoft Intune への移行を完了するには、次のアクセス許可を付与することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-130">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="3e3e7-131">アプリの追加と割り当てに使用するための、Microsoft Intune のアプリ展開機能へのアクセス</span><span class="sxs-lookup"><span data-stu-id="3e3e7-131">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="3e3e7-132">Packagers がアプリをテストできるようにするためのグループ、ユーザーアカウント、およびライセンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-132">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="3e3e7-133">MCS は、これらのアクセス許可を使用して、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-133">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="3e3e7-134">Microsoft マネージドデスクトップ用に構成された仮想マシン上でアプリが動作することを確認する</span><span class="sxs-lookup"><span data-stu-id="3e3e7-134">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="3e3e7-135">ユーザーに展開するためにアプリを Microsoft Intune にアップロードする</span><span class="sxs-lookup"><span data-stu-id="3e3e7-135">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="3e3e7-136">これらのアクセス許可がないと、MCS は先に進むことができますが、アプリケーションを環境にアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3e3e7-136">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


