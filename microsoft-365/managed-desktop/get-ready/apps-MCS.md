---
title: Microsoft コンサルティング サービスを使用する
description: MCS を使用してアプリをパッケージ化するための準備と手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 7a967f5e4b2678b55ed87f2eaa68590703c55805
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840888"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="6e2fb-104">Microsoft コンサルティング サービスを使用する</span><span class="sxs-lookup"><span data-stu-id="6e2fb-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="6e2fb-105">Microsoft Consulting Services (MCS) に参加して、アプリをパッケージ化して、ユーザーと一緒に使用Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="6e2fb-106">詳細については、アカウント担当者と一緒に MCS に問い合わせ、特定のアプリ パッケージ プロジェクトの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="6e2fb-107">役割と責任</span><span class="sxs-lookup"><span data-stu-id="6e2fb-107">Roles and responsibilities</span></span>

<span data-ttu-id="6e2fb-108">MCS アプリパッケージを使用するには、 **次の要素を指定する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="6e2fb-109">ソース インストーラー ファイル (たとえば、setup.exeまたは.msi)。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="6e2fb-110">最終的なインストールの外観に関する詳細を指定するインストール手順。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="6e2fb-111">たとえば、アプリへのデスクトップ ショートカットがある必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="6e2fb-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="6e2fb-112">アプリの表示設定は何ですか?</span><span class="sxs-lookup"><span data-stu-id="6e2fb-112">What should the app's visibility be?</span></span> <span data-ttu-id="6e2fb-113">アプリがサーバーに接続する必要があります。その場合、どちらに接続しますか?</span><span class="sxs-lookup"><span data-stu-id="6e2fb-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="6e2fb-114">詳細については、「アプリケーション パッケージ [要求テンプレート」を参照してください](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="6e2fb-115">独自の受け入れテストを実行して、環境内で必要に応じてアプリが動作する方法を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="6e2fb-116">**MCS は、次のアクションを処理します。**</span><span class="sxs-lookup"><span data-stu-id="6e2fb-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="6e2fb-117">アプリが環境内で禁止または制限されているかどうかをMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="6e2fb-118">アプリのインストール、開始、アンインストールをテストして、アプリとの互換性をWindows 10。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="6e2fb-119">MCS で互換性の問題が検出された場合、アプリは修復のために [App Assure](/fasttrack/products-and-capabilities#app-assure) プログラムに渡されます。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-119">If MCS discovers a compatibility issue, they will hand off the app to the [App Assure](/fasttrack/products-and-capabilities#app-assure) program for remediation.</span></span>
- <span data-ttu-id="6e2fb-120">アプリを仕様にパッケージ化し、アプリの展開をテストするには、アプリを使用Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="6e2fb-121">アプリの配信スケジュール</span><span class="sxs-lookup"><span data-stu-id="6e2fb-121">App delivery schedule</span></span>

<span data-ttu-id="6e2fb-122">アプリ情報をポータルにアップロードして、パッケージ化プロセスMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="6e2fb-123">パッケージ チームは、毎週木曜日に新しい申請を確認します。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="6e2fb-124">確認とパッケージ化の後、パッケージ化されたアプリは次の金曜日に配信されます。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="6e2fb-125">週に最大 5 つのアプリをパッケージ化して開始できますが、サービスはニーズに合わせて拡張できます。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![木曜日 (この例では 21 日) のアプリの流入、次の日のメディア検証、次の月曜日 (25 日) のパッケージ化、および後続の金曜日 (29 日) のアプリ配信を示すカレンダー](../../media/MCS-cal.png)

<span data-ttu-id="6e2fb-127">アプリが配信された後に通知されます。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="6e2fb-128">この時点で、受け入れテストを実行し、ポータルで作業を承認するには 21 Microsoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="6e2fb-129">受け入れテスト中にアプリに関する問題を発見した場合は、Microsoft マネージド デスクトップ ポータルでアプリを拒否し、問題を理解して解決するために MCS パッケージーと電子メールで接続されます。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="6e2fb-130">アカウントと環境のテスト</span><span class="sxs-lookup"><span data-stu-id="6e2fb-130">Testing accounts and environment</span></span>

<span data-ttu-id="6e2fb-131">パッケージ チームがパッケージ への移行を完了Microsoft Intune、特定のアクセス許可を提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>

- <span data-ttu-id="6e2fb-132">パッケージMicrosoft Intuneアプリを追加および割り当てるアプリの展開機能へのアクセス</span><span class="sxs-lookup"><span data-stu-id="6e2fb-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span>
- <span data-ttu-id="6e2fb-133">パッケージ作成者がアプリをテストできるテスト グループ、ユーザー アカウント、ライセンス</span><span class="sxs-lookup"><span data-stu-id="6e2fb-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="6e2fb-134">MCS は、これらのアクセス許可を使用して次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-134">MCS will use those permissions to perform the following actions:</span></span>

- <span data-ttu-id="6e2fb-135">アプリが仮想マシン用に構成された仮想マシンで動作Microsoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="6e2fb-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
- <span data-ttu-id="6e2fb-136">ユーザーに展開Microsoft Intuneアプリをアップロードする</span><span class="sxs-lookup"><span data-stu-id="6e2fb-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="6e2fb-137">これらのアクセス許可がない場合、MCS は前進できますが、アプリケーションを環境にアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6e2fb-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>
