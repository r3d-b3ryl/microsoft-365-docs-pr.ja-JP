---
title: Microsoft コンサルティング サービスを使用する
description: アプリケーションをパッケージ化するために MCS と連携するための準備と手順
keywords: Microsoft マネージドデスクトップ、Microsoft 365、service、ドキュメント、アプリ、MCS、パッケージ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0cb4da85b5548ced757197a3af818e212b065b47
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085943"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="c1f81-104">Microsoft コンサルティング サービスを使用する</span><span class="sxs-lookup"><span data-stu-id="c1f81-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="c1f81-105">Microsoft コンサルティングサービス (MCS) と協力して、Microsoft マネージドデスクトップで使用するためにアプリをパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="c1f81-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="c1f81-106">詳細については、アカウント担当者と連携して MCS と連絡をとって、特定のアプリパッケージプロジェクトの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1f81-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="c1f81-107">役割と責任</span><span class="sxs-lookup"><span data-stu-id="c1f81-107">Roles and responsibilities</span></span>

<span data-ttu-id="c1f81-108">MCS アプリパッケージを使用するには、**次の要素を提供する必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="c1f81-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="c1f81-109">ソースインストーラファイル (例: setup.exe または .msi)。</span><span class="sxs-lookup"><span data-stu-id="c1f81-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="c1f81-110">インストール手順で、最終的なインストール方法の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1f81-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="c1f81-111">たとえば、アプリにデスクトップショートカットがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1f81-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="c1f81-112">アプリの可視性をどのようにする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c1f81-112">What should the app's visibility be?</span></span> <span data-ttu-id="c1f81-113">アプリをサーバーに接続し、その場合はどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="c1f81-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="c1f81-114">詳細については、「[アプリケーションパッケージ要求テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1f81-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="c1f81-115">アプリが環境内で必要なときに動作することを確認するために、独自の受け入れテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1f81-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="c1f81-116">**MCS は、次の操作を行います。**</span><span class="sxs-lookup"><span data-stu-id="c1f81-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="c1f81-117">Microsoft マネージドデスクトップ環境でアプリが禁止または制限されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c1f81-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="c1f81-118">Windows 10 との互換性を確保するために、アプリのインストール、開始、アンインストールをテストします。</span><span class="sxs-lookup"><span data-stu-id="c1f81-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="c1f81-119">MCS が互換性の問題を検出した場合は、アプリを[デスクトップアプリ](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure)に渡して、修復のためのプログラムを確実に実行します。</span><span class="sxs-lookup"><span data-stu-id="c1f81-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="c1f81-120">アプリを仕様にパッケージ化し、Microsoft Intune を使用してアプリの展開をテストします。</span><span class="sxs-lookup"><span data-stu-id="c1f81-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="c1f81-121">アプリの配信スケジュール</span><span class="sxs-lookup"><span data-stu-id="c1f81-121">App delivery schedule</span></span>

<span data-ttu-id="c1f81-122">アプリの情報を Microsoft マネージドデスクトップポータルにアップロードして、パッケージ化プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="c1f81-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="c1f81-123">パッケージチームは、毎週木曜日に新しい提出をレビューします。</span><span class="sxs-lookup"><span data-stu-id="c1f81-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="c1f81-124">レビューとパッケージ化後、パッケージ化されたアプリは次の金曜日に配信されます。</span><span class="sxs-lookup"><span data-stu-id="c1f81-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="c1f81-125">1週間に最大5つのアプリを開始するためのパッケージを作成できますが、サービスはニーズに合わせて拡張できます。</span><span class="sxs-lookup"><span data-stu-id="c1f81-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![木曜日にアプリケーションのインフロー (この例では 21)、次の日にメディア検証、次の月曜日にパッケージ化 (25)、以降の金曜日にアプリの配信を示すカレンダー (29 日)](../../media/MCS-cal.png)

<span data-ttu-id="c1f81-127">アプリが配信されると、通知されます。</span><span class="sxs-lookup"><span data-stu-id="c1f81-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="c1f81-128">その時点で、承認テストを実行し、Microsoft マネージドデスクトップポータルで作業を行うことができるのは、21日です。</span><span class="sxs-lookup"><span data-stu-id="c1f81-128">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="c1f81-129">受け入れテストの間にアプリに関して何らかの問題が見つかった場合は、Microsoft マネージドデスクトップポータルでアプリを拒否すると、問題を把握して解決するために、メールで MCS パッケージャーに接続されます。</span><span class="sxs-lookup"><span data-stu-id="c1f81-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="c1f81-130">アカウントと環境のテスト</span><span class="sxs-lookup"><span data-stu-id="c1f81-130">Testing accounts and environment</span></span>

<span data-ttu-id="c1f81-131">パッケージ化チームが Microsoft Intune への移行を完了するには、次のアクセス許可を付与することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c1f81-131">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="c1f81-132">アプリの追加と割り当てに使用するための、Microsoft Intune のアプリ展開機能へのアクセス</span><span class="sxs-lookup"><span data-stu-id="c1f81-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="c1f81-133">Packagers がアプリをテストできるようにするためのグループ、ユーザーアカウント、およびライセンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="c1f81-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="c1f81-134">MCS は、これらのアクセス許可を使用して、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1f81-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="c1f81-135">Microsoft マネージドデスクトップ用に構成された仮想マシン上でアプリが動作することを確認する</span><span class="sxs-lookup"><span data-stu-id="c1f81-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="c1f81-136">ユーザーに展開するためにアプリを Microsoft Intune にアップロードする</span><span class="sxs-lookup"><span data-stu-id="c1f81-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="c1f81-137">これらのアクセス許可がないと、MCS は先に進むことができますが、アプリケーションを環境にアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c1f81-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


