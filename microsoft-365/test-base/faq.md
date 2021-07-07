---
title: テスト ベースに関する FAQ
description: よく寄せられる質問を確認する
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323380"
---
# <a name="test-base-faq"></a><span data-ttu-id="2b343-103">テスト ベースに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="2b343-103">Test Base FAQ</span></span>

<span data-ttu-id="2b343-104">**Q: パッケージをテストベース チームに提出する方法**</span><span class="sxs-lookup"><span data-stu-id="2b343-104">**Q: How do we submit our packages to Test Base team?**</span></span>

<span data-ttu-id="2b343-105">**A:** セルフサービス ポータルを使用して、パッケージを Test Base 環境に直接送信します。</span><span class="sxs-lookup"><span data-stu-id="2b343-105">**A:** Submit your packages directly to the Test Base environment using our self-serve portal.</span></span>

<span data-ttu-id="2b343-106">アプリケーション パッケージを提出するには [、Azure Portal](https://www.aka.ms/testbaseportal "テストベースのホームページ") に移動し、セルフサービスのテスト ベース ポータル ダッシュボードを介して、アプリケーションのバイナリ、依存関係、およびテスト スクリプトを含む zip 形式のフォルダーをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="2b343-106">To submit your application package, navigate to the [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") and upload a zipped folder containing your application's binaries, dependencies, and test scripts via the self-serve Test Base portal dashboard.</span></span> 

<span data-ttu-id="2b343-107">詳細については、オンボーディング ユーザー ガイドを参照するか、サポートと詳細については、弊社の <testbasepreview@microsoft.com> チームにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="2b343-107">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="2b343-108">**Q: アウトオブボックス (OOB) テストとは**</span><span class="sxs-lookup"><span data-stu-id="2b343-108">**Q: What are Out-of-box (OOB) tests?**</span></span>

<span data-ttu-id="2b343-109">**A:** 標準 (OOB) テストは標準化され、既定のテストは、アプリケーション パッケージがインストールされ、起動され、30 回閉じ、アンインストールされる場所で実行されます。</span><span class="sxs-lookup"><span data-stu-id="2b343-109">**A:** Out-of-box (OOB) tests are standardized, default test runs where application packages are installed, launched and closed thirty (30) times, and then uninstalled.</span></span> 

<span data-ttu-id="2b343-110">Test Base 用に作成されたパッケージには、インストール、起動、閉じる、必要に応じてアンインストール スクリプトのテスト スクリプトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b343-110">The packages created for Test Base will have the following test scripts: install, launch, close, and optionally the uninstall script.</span></span> 

<span data-ttu-id="2b343-111">アウトオブボックス (OOB) テストでは、アプリケーション上で標準化されたテレメトリを提供し、さまざまなビルドWindowsできます。</span><span class="sxs-lookup"><span data-stu-id="2b343-111">The Out-of-box (OOB) tests provide you with standardized telemetry on your application to compare across Windows builds.</span></span>

<span data-ttu-id="2b343-112">**Q: アウトオブボックス テスト (インストール、起動、閉じる、テスト スクリプトのアンインストール) の外部でテストを提出できますか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-112">**Q: Can we submit tests outside of the Out-of-box tests (install, launch, close, uninstall test scripts)?**</span></span>

<span data-ttu-id="2b343-113">**A:** はい、ユーザーはセルフサービス ポータル ダッシュボードを介して **機能** テスト用のアプリケーション パッケージをアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2b343-113">**A:** Yes, customers can also upload application packages for **functional tests** via the self-serve portal dashboard.</span></span>
<span data-ttu-id="2b343-114">**機能テストは** 、ユーザーがスクリプトを実行してアプリケーションでカスタム機能を実行できるテストです。</span><span class="sxs-lookup"><span data-stu-id="2b343-114">**Functional tests** are tests that enable customers execute their scripts to run custom functionality on their application.</span></span>


## <a name="testing"></a><span data-ttu-id="2b343-115">テスト</span><span class="sxs-lookup"><span data-stu-id="2b343-115">Testing</span></span>

<span data-ttu-id="2b343-116">**Q: 機能テストをサポートしていますか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-116">**Q: Do you support functional tests?**</span></span>

<span data-ttu-id="2b343-117">**A:** はい、Test Base は機能テストをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2b343-117">**A:** Yes, Test Base supports functional tests.</span></span> <span data-ttu-id="2b343-118">機能テストは、お客様がスクリプトを実行してアプリケーションでカスタム機能を実行できるテストです。</span><span class="sxs-lookup"><span data-stu-id="2b343-118">Functional tests are tests that enable our customers execute their scripts to run custom functionality on their application.</span></span> 

<span data-ttu-id="2b343-119">機能テスト用にアプリケーション パッケージを提出するには、セルフサービス ポータル ダッシュボードを介して、アプリケーションのバイナリ、依存関係、およびテスト スクリプトを含む zip フォルダーをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="2b343-119">To submit your application package for functional testing, simply upload the zipped folder containing your application's binaries, dependencies, and test scripts via our self-serve portal dashboard.</span></span> 

<span data-ttu-id="2b343-120">詳細については、オンボーディング ユーザー ガイドを参照するか、サポートと詳細については、弊社の <testbasepreview@microsoft.com> チームにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="2b343-120">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="2b343-121">**Q: Test Base はテスト データを処理する方法を示します。**</span><span class="sxs-lookup"><span data-stu-id="2b343-121">**Q: How does Test Base handle our test data?**</span></span>

<span data-ttu-id="2b343-122">**A:** Test Base は、Azure 環境上のテスト データを安全に収集および管理します。</span><span class="sxs-lookup"><span data-stu-id="2b343-122">**A:** Test Base securely collects and manages your test data on the Azure environment.</span></span> 

<span data-ttu-id="2b343-123">**Q: テスト ベースは自動テストをサポートできますか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-123">**Q: Can Test Base support our automated tests?**</span></span>

<span data-ttu-id="2b343-124">はい、Test Base は自動テストをサポートしますが、サービス機能のため、現時点では手動テストはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2b343-124">Yes, Test Base supports automated tests however, we do not support manual tests at this time due to service capabilities.</span></span>

<span data-ttu-id="2b343-125">**Q: 自動テストの言語とフレームワークは何をサポートしていますか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-125">**Q: What languages and frameworks of automated tests do you support?**</span></span>

<span data-ttu-id="2b343-126">**A:** すべての言語とフレームワークをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2b343-126">**A:** We support all languages and frameworks.</span></span> <span data-ttu-id="2b343-127">PowerShell を使用してすべてのスクリプトを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2b343-127">We invoke all scripts through PowerShell.</span></span> 

<span data-ttu-id="2b343-128">また、必要なフレームワークの依存バイナリを提供 (アップロード) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b343-128">You will also need to provide (upload) the dependent binaries of the required framework.</span></span>

<span data-ttu-id="2b343-129">**Q: テスト ベースでテスト結果が提供される時間はどのくらいですか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-129">**Q: How soon does Test Base provide test results?**</span></span>

<span data-ttu-id="2b343-130">**A:** プレリリース ビルドに対して実行するテストごとに [、Azure Portal](https://www.aka.ms/testbaseportal "テストベースのホームページ") ダッシュボードで 48 時間以内に結果を提供します。</span><span class="sxs-lookup"><span data-stu-id="2b343-130">**A:** For each test that we run against the pre-release builds, we will provide results within 48 hours on your [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") dashboard.</span></span>

<span data-ttu-id="2b343-131">**Q: インストール後に再起動できますか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-131">**Q: Can you reboot after install?**</span></span>

<span data-ttu-id="2b343-132">**A:** はい、インストール後の再起動をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2b343-132">**A:** Yes, our process supports rebooting after installation.</span></span> <span data-ttu-id="2b343-133">オンボーディング ポータルでタスクを設定する場合は、必ず [オプション設定] ドロップ リストから **このオプションを** 選択してください。</span><span class="sxs-lookup"><span data-stu-id="2b343-133">Be sure to select this option from the “Optional settings” drop list when setting your **Tasks** on the onboarding portal.</span></span>

<span data-ttu-id="2b343-134">アウトオブボックス (OOB) テストでは、Install スクリプトに再起動が必要かどうかを _指定できます。_</span><span class="sxs-lookup"><span data-stu-id="2b343-134">For Out-of-box (OOB) tests, you can specify whether a reboot is needed for the _Install script._</span></span>

![画像の再起動](Media/reboot.png)

<span data-ttu-id="2b343-136">機能テストの場合は、追加するスクリプトごとに再起動が必要かどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2b343-136">While for functional tests, you can specify whether a reboot is required for each script that is added.</span></span>

![機能テストを選択する方法](Media/functionalreboot.png)

<span data-ttu-id="2b343-138">**Q: サポートWindowsバージョンは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-138">**Q: What Windows versions do you support?**</span></span>

<span data-ttu-id="2b343-139">**A:** 現在、Windows 10 クライアント、Windows Server 2016、Windows Server 2016 Core バージョン、Windows Server 2019、Windows Server 2019 Core バージョンをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2b343-139">**A:** We currently support Windows 10 clients, Windows Server 2016, Windows Server 2016 Core version, Windows Server 2019, and Windows Server 2019 Core version.</span></span>

<span data-ttu-id="2b343-140">**Q: セキュリティ更新プログラムのテストと機能更新プログラムのテストの違いは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-140">**Q: What is the difference between Security Update tests and Feature Update tests?**</span></span>

<span data-ttu-id="2b343-141">**A:** セキュリティ更新プログラムのテストでは、ユーザーが **<ins></ins>** 常に安全で保護された状態を保つことに重点を置Windowsの月次プレリリース セキュリティ更新プログラムに対してテストします。</span><span class="sxs-lookup"><span data-stu-id="2b343-141">**A:** For Security update tests, we test against the **<ins>monthly pre-release security updates</ins>** on Windows which are focused on keeping our users always secure and protected.</span></span> <span data-ttu-id="2b343-142">機能更新プログラムのテストでは、2 **<ins></ins>** 年に 1 回のリリース前の機能更新プログラムに対してテストを行い、この更新プログラムで新しい機能と機能を導入Windows。</span><span class="sxs-lookup"><span data-stu-id="2b343-142">For the Feature update tests, we test against the **<ins>bi-annual pre-release feature updates</ins>** which introduces new features and capabilities on Windows.</span></span>

## <a name="debugging-options"></a><span data-ttu-id="2b343-143">デバッグ オプション</span><span class="sxs-lookup"><span data-stu-id="2b343-143">Debugging options</span></span>

<span data-ttu-id="2b343-144">**Q: 障害が発生した場合に仮想マシン (VM) にアクセスできますか?テストベースは何を共有しますか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-144">**Q: Do we get access to the Virtual Machines (VMs) in case of failures? What does Test Base share?**</span></span>

<span data-ttu-id="2b343-145">**A:** サービスに準拠し、リリース前の更新プログラムをセキュリティで保護するには、Microsoft だけが VM にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2b343-145">**A:** For the service to be compliant and the pre-release updates be secure, only Microsoft has access to the VMs.</span></span> <span data-ttu-id="2b343-146">ただし、テスト結果とその他のテスト 指標は、クラッシュおよびハング信号、信頼性メトリック、メモリ、CPU 使用率など、ポータル ダッシュボードで表示できます。また、ダッシュボードでテスト実行のログを生成して提供し、ダウンロードと分析を行います。</span><span class="sxs-lookup"><span data-stu-id="2b343-146">However, customers can view test results and other test metrics on their portal dashboard, including crash and hang signals, reliability metrics, memory and CPU utilization etc. We also generate and provide logs of test runs on the dashboard for download and further analysis.</span></span> 

<span data-ttu-id="2b343-147">必要に応じてクラッシュ デバッグ用のメモリ ダンプも提供できます。</span><span class="sxs-lookup"><span data-stu-id="2b343-147">We can also provide memory dumps for crash debugging as needed.</span></span>

<span data-ttu-id="2b343-148">**Q: テスト中に問題が見つかった場合、これらの問題を解決するための次の手順は何ですか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-148">**Q: If there are issues found during the testing, what are the next steps to resolve these issues?**</span></span>

<span data-ttu-id="2b343-149">**A:** テスト ベース チームは、最初のトリアージ プロセスを実行してエラーの根本原因を特定し、その結果に応じて、デバッグのために Microsoft 内の顧客または内部チームにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="2b343-149">**A:** The Test Base team will perform an initial triage process to determine the root cause of the error, and then depending on our findings, we will route to the customer or internal teams within Microsoft for debugging.</span></span> 

<span data-ttu-id="2b343-150">お客様と常に密接に取り組み、問題を解決するために共同修復を行います。</span><span class="sxs-lookup"><span data-stu-id="2b343-150">We always work closely with our customers in joint remediation to resolve any issues.</span></span> 

<span data-ttu-id="2b343-151">**Q: 問題が解決するまで、Microsoft はセキュリティ 更新プログラムのリリースを保持していますか?使用可能な代替解像度は何ですか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-151">**Q: Does Microsoft hold the release of the security patch until the issue is resolved? What alternate resolutions are available?**</span></span>

<span data-ttu-id="2b343-152">**A:** Test Base の目標は、共同エンド のお客様が問題に直面しなかからなかろうという点です。</span><span class="sxs-lookup"><span data-stu-id="2b343-152">**A:** The goal of Test Base is to ensure our joint end customers do not face any issues.</span></span> <span data-ttu-id="2b343-153">ソフトウェア ベンダーと一緒に、リリース前に問題に対処しますが、修正が不可能な場合は、シムやブロックなどの他の解決策があります。</span><span class="sxs-lookup"><span data-stu-id="2b343-153">We will work hard with Software Vendors to address any issues before the release, but in case the fix is not feasible we have other resolutions such as shims and blocks.</span></span>

## <a name="miscellaneous"></a><span data-ttu-id="2b343-154">その他</span><span class="sxs-lookup"><span data-stu-id="2b343-154">Miscellaneous</span></span>

<span data-ttu-id="2b343-155">**Q: サービスはプレムサーバーでどのように動作しますか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-155">**Q: How will the service work with an on-prem server?**</span></span>

<span data-ttu-id="2b343-156">**A:** 現在、オンプレム サーバーのサポートは提供されていません。</span><span class="sxs-lookup"><span data-stu-id="2b343-156">**A:** We currently do not provide support for on-prem servers.</span></span> <span data-ttu-id="2b343-157">ただし、サーバーが HTTP エンドポイントを公開している場合は、インターネットを使用して接続できます。</span><span class="sxs-lookup"><span data-stu-id="2b343-157">However, if the server is exposing HTTP endpoint, we can connect to it over the internet.</span></span>

<span data-ttu-id="2b343-158">**Q: Who VM をホストしますか。**</span><span class="sxs-lookup"><span data-stu-id="2b343-158">**Q: Who hosts the VMs?**</span></span>

<span data-ttu-id="2b343-159">**A:** Microsoft は、このサービスの VM をプロビジョニングし、その負荷を顧客から受け取っています。</span><span class="sxs-lookup"><span data-stu-id="2b343-159">**A:** Microsoft provisions the VM for this service, taking the load of doing so from the customer.</span></span>

<span data-ttu-id="2b343-160">**Q: このサービスは Web、モバイル、またはデスクトップ アプリケーションをサポートしていますか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-160">**Q: Does this service support web, mobile, or desktop applications?**</span></span>

<span data-ttu-id="2b343-161">**A:** 現時点では、デスクトップ アプリケーションに焦点を当てしていますが、今後 Web アプリケーションをオンボードする予定がありますが、現時点ではモバイル アプリケーションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2b343-161">**A:** Currently, our focus is on desktop applications, however, we have plans to onboard web applications in the future, but we do not support mobile applications at this time.</span></span>

<span data-ttu-id="2b343-162">**Q: テスト ベースと SUVP の違いは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="2b343-162">**Q: What is the difference between Test Base and SUVP?**</span></span>

<span data-ttu-id="2b343-163">**A:** テストベースとSUVPの最大の違いは、検証のためにアプリケーションをテストベース Azure 環境にオンボードするパートナーが、テスト自体を実行する代わりにプレリリース更新プログラムに対して実行される点です。</span><span class="sxs-lookup"><span data-stu-id="2b343-163">**A:** The biggest difference between Test Base and SUVP is that our partners onboard their applications onto the Test Base Azure environment for validation runs against pre-release updates instead of carrying out the tests themselves.</span></span> 

<span data-ttu-id="2b343-164">プレリリースのセキュリティ更新プログラムのテストに加えて、プラットフォームでのプレリリース機能更新プログラムのテストもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2b343-164">In addition to pre-release security updates testing, we support pre-release feature updates testing on our platform.</span></span> <span data-ttu-id="2b343-165">ロードマップには、他にも多くの種類の更新プログラムと OS テストがあります。</span><span class="sxs-lookup"><span data-stu-id="2b343-165">We have many other types of updates and OS testing on our roadmap.</span></span>

<span data-ttu-id="2b343-166">**Q: サービスに関連付けられているコストはありますか。**</span><span class="sxs-lookup"><span data-stu-id="2b343-166">**Q: Is there a cost associated with the service?**</span></span>

<span data-ttu-id="2b343-167">**A:** Test Base サービスは、一般提供 (GA) までユーザーに無料で提供されます。</span><span class="sxs-lookup"><span data-stu-id="2b343-167">**A:** The Test Base service will be free to users until General Availability (GA).</span></span> <span data-ttu-id="2b343-168">その時点で、すべての顧客に対して有効になるコスト構造を発表します。</span><span class="sxs-lookup"><span data-stu-id="2b343-168">At that time, we will announce a cost structure that will be in effect for all customers.</span></span> 

<span data-ttu-id="2b343-169">**Q: テスト ベースに関するフィードバックを提供する方法**</span><span class="sxs-lookup"><span data-stu-id="2b343-169">**Q: How can I provide feedback about Test Base?**</span></span>

<span data-ttu-id="2b343-170">**A:** テスト ベースに関するフィードバックを共有するには、ポータルの左下にある [フィードバック] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="2b343-170">**A:** To share your feedback about Test Base, select the **Feedback** icon at the bottom left of the portal.</span></span> <span data-ttu-id="2b343-171">Microsoft がフィードバックをよりよく理解するために、申請にスクリーンショットを含める。</span><span class="sxs-lookup"><span data-stu-id="2b343-171">Include a screenshot with your submission to help Microsoft better understand your feedback.</span></span> 

<span data-ttu-id="2b343-172">また、製品の提案を提出し、他のアイデアをアップヴォテすることができます <testbasepreview@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="2b343-172">You can also submit product suggestions and upvote other ideas at <testbasepreview@microsoft.com>.</span></span>
