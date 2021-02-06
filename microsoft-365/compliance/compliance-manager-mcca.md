---
title: コンプライアンス マネージャー向け Microsoft Compliance Configuration Analyzer
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンス構成アナライザーを使用して、Microsoft コンプライアンス マネージャーを迅速に開始および実行する方法について説明します。
ms.openlocfilehash: 86c4b04deb8313f3013a6d9ad349c0f4112db773
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122397"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="be38a-103">コンプライアンス マネージャー用の Microsoft Compliance Configuration Analyzer (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="be38a-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="be38a-104">**この記事では、次の情報を参照してください。** Microsoft Compliance Configure Analyzer ツールをインストールして実行し、Microsoft コンプライアンス 管理をすぐに開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be38a-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="be38a-105">Microsoft Compliance Configuration Analyzer (MCCA) (プレビュー) の概要</span><span class="sxs-lookup"><span data-stu-id="be38a-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="be38a-106">Microsoft Compliance Configuration Analyzer (MCCA) は、Microsoft コンプライアンス マネージャーの使用を開始するのに役立つプレビュー [ツールです](compliance-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="be38a-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="be38a-107">MCCA は、組織の現在の構成をフェッチし、Microsoft 365 の推奨ベスト プラクティスに対して検証する PowerShell ベースのユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="be38a-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="be38a-108">これらのベスト プラクティスは、データ保護とデータ ガバナンスの主要な規制と基準を含む一連のコントロールに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="be38a-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="be38a-109">MCCA は、コンプライアンス 管理の改善アクションが現在の Microsoft 365 環境に適用されるのを迅速に確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="be38a-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="be38a-110">MCCA によって識別される各アクションには、実装に関する推奨事項が示されます。コンプライアンス マネージャーへの直接リンクと、修正アクションの実行を開始する該当するソリューションへの直接リンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="be38a-111">MCCA を理解する追加のリソースは [、GitHub の README の手順にアクセスする方法です](https://github.com/OfficeDev/MCCA#overview)。</span><span class="sxs-lookup"><span data-stu-id="be38a-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="be38a-112">このページでは、前提条件に関する詳細情報を提供し、完全なインストール手順を示します。</span><span class="sxs-lookup"><span data-stu-id="be38a-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="be38a-113">このページにアクセスするために GitHub アカウントは必要ない。</span><span class="sxs-lookup"><span data-stu-id="be38a-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="be38a-114">**可用性**: MCCA は、Office 365 ライセンスと Microsoft 365 ライセンス、および米国政府機関コミュニティ (GCC) Moderate のお客様のすべての組織で利用できます。GCC High のお客様にサービスを拡張する計画が進行中です。</span><span class="sxs-lookup"><span data-stu-id="be38a-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate customers, with plans underway to expand service to to GCC High customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="be38a-115">MCCA をインストールしてレポートを実行する</span><span class="sxs-lookup"><span data-stu-id="be38a-115">Install MCCA and run a report</span></span>

<span data-ttu-id="be38a-116">MCCA ツールは、次のコマンドを使用してWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="be38a-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="be38a-117">ツールをダウンロードしてインストールしたら、レポートを実行するためにこれらの手順を繰り返す必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="be38a-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="be38a-118">MCCA を開くたび、ログイン資格情報の入力を求め、新しい更新されたレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="be38a-119">手順 1: インストールWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be38a-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="be38a-120">まず、PowerShell ギャラリーで利用できる Exchange Online PowerShell モジュール (v2.0.3 以上) が必要です。</span><span class="sxs-lookup"><span data-stu-id="be38a-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="be38a-121">[インストール手順を取得します](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)。</span><span class="sxs-lookup"><span data-stu-id="be38a-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="be38a-122">手順 2: MCCA をインストールする</span><span class="sxs-lookup"><span data-stu-id="be38a-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="be38a-123">MCCA をインストールするには、管理者モードで PowerShell を使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="be38a-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="be38a-124">次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="be38a-124">Follow the steps below:</span></span>

1. <span data-ttu-id="be38a-125">Windows の [スタート] **ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="be38a-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="be38a-126">**「PowerShell」と** 入力し、アプリケーションを右クリック **Windows PowerShell、[管理者** として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="be38a-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="be38a-127">コマンド プロンプトで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="be38a-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="be38a-128">手順 3: レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="be38a-128">Step 3: Run a report</span></span>

<span data-ttu-id="be38a-129">MCCA をインストールした後、MCCA を実行してレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="be38a-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="be38a-130">レポートを実行するには:</span><span class="sxs-lookup"><span data-stu-id="be38a-130">To run a report:</span></span>

1. <span data-ttu-id="be38a-131">PowerShell を開く</span><span class="sxs-lookup"><span data-stu-id="be38a-131">Open PowerShell</span></span>
2. <span data-ttu-id="be38a-132">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be38a-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```
3. <span data-ttu-id="be38a-133">MCCA を実行すると、初期バージョン チェックが実行され、資格情報が要求されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-133">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="be38a-134">[ユーザー名の入力] プロンプトで、Microsoft 365 アカウントのメール アドレスでサインインします (レポートを作成する対象の役割[を表示します](#role-based-reporting))。</span><span class="sxs-lookup"><span data-stu-id="be38a-134">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="be38a-135">次に、パスワード プロンプトでパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="be38a-135">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="be38a-136">レポートの生成に約 2 ~ 5 分かかります。</span><span class="sxs-lookup"><span data-stu-id="be38a-136">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="be38a-137">完了すると、ブラウザー ウィンドウが開き、HTML レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-137">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="be38a-138">ツールを実行すると、資格情報が要求され、新しいレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-138">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="be38a-139">このレポートは、次のディレクトリにローカルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-139">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="be38a-140">C:\Users \<username> \AppData\Local\Microsoft\MCCA。</span><span class="sxs-lookup"><span data-stu-id="be38a-140">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="be38a-141">このディレクトリから、以前に生成されたレポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="be38a-141">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="be38a-142">レポートについて</span><span class="sxs-lookup"><span data-stu-id="be38a-142">Understanding your report</span></span>

<span data-ttu-id="be38a-143">レポートには、生成日時に基づくデータが反映されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-143">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="be38a-144">上部のセクションでは、生成された時間、組織名、テナント ID に関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-144">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="be38a-145">地理位置情報ベースのレポート</span><span class="sxs-lookup"><span data-stu-id="be38a-145">Geolocation-based reporting</span></span>

<span data-ttu-id="be38a-146">[ **メモ** ] セクションには、テナントの地理的な場所に基づいてレポートがカスタマイズされたと表示されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-146">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="be38a-147">このツールに記載されている推奨事項は、お客様の国または地域に固有の推奨事項です。</span><span class="sxs-lookup"><span data-stu-id="be38a-147">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="be38a-148">地理位置情報の選択は、その地理位置情報に関連する機密情報の種類 (SIT) を評価し、お客様の国または地域に合ったレポートを生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-148">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="be38a-149">テナント内のデータに基づいて地理位置情報を選択します。</span><span class="sxs-lookup"><span data-stu-id="be38a-149">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="be38a-150">レポートの位置情報を変更するには、地理位置情報 (-Geo) 入力パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be38a-150">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="be38a-151">テナントに適用可能な 1 つ以上の地理位置情報を選択できます。</span><span class="sxs-lookup"><span data-stu-id="be38a-151">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="be38a-152">特定の場所に基づいてレポートを実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="be38a-152">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="be38a-153">PowerShell を開く</span><span class="sxs-lookup"><span data-stu-id="be38a-153">Open PowerShell</span></span>
2. <span data-ttu-id="be38a-154">特定の地域を指定するには、国または地域に対応する次の表の番号を使用してコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be38a-154">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="be38a-155">複数の数値をコンマで区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="be38a-155">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="be38a-156">たとえば、次のコマンドレットは、ユーザーと日本に対してカスタマイズAsia-Pacific実行します。</span><span class="sxs-lookup"><span data-stu-id="be38a-156">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="be38a-157">Input</span><span class="sxs-lookup"><span data-stu-id="be38a-157">Input</span></span> |  <span data-ttu-id="be38a-158">国または地域</span><span class="sxs-lookup"><span data-stu-id="be38a-158">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="be38a-159">1 </span><span class="sxs-lookup"><span data-stu-id="be38a-159">1</span></span> | <span data-ttu-id="be38a-160">アジア太平洋</span><span class="sxs-lookup"><span data-stu-id="be38a-160">Asia-Pacific</span></span> |
  | <span data-ttu-id="be38a-161">2 </span><span class="sxs-lookup"><span data-stu-id="be38a-161">2</span></span> | <span data-ttu-id="be38a-162">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="be38a-162">Australia</span></span> |
  | <span data-ttu-id="be38a-163">3 </span><span class="sxs-lookup"><span data-stu-id="be38a-163">3</span></span> | <span data-ttu-id="be38a-164">カナダ</span><span class="sxs-lookup"><span data-stu-id="be38a-164">Canada</span></span> |
  | <span data-ttu-id="be38a-165">4 </span><span class="sxs-lookup"><span data-stu-id="be38a-165">4</span></span> | <span data-ttu-id="be38a-166">ヨーロッパ (フランスを除く) / 中東/アフリカ</span><span class="sxs-lookup"><span data-stu-id="be38a-166">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="be38a-167">5 </span><span class="sxs-lookup"><span data-stu-id="be38a-167">5</span></span> | <span data-ttu-id="be38a-168">フランス</span><span class="sxs-lookup"><span data-stu-id="be38a-168">France</span></span> |
  | <span data-ttu-id="be38a-169">6 </span><span class="sxs-lookup"><span data-stu-id="be38a-169">6</span></span> | <span data-ttu-id="be38a-170">インド</span><span class="sxs-lookup"><span data-stu-id="be38a-170">India</span></span> |
  | <span data-ttu-id="be38a-171">7 </span><span class="sxs-lookup"><span data-stu-id="be38a-171">7</span></span> | <span data-ttu-id="be38a-172">日本</span><span class="sxs-lookup"><span data-stu-id="be38a-172">Japan</span></span> |
  | <span data-ttu-id="be38a-173">8 </span><span class="sxs-lookup"><span data-stu-id="be38a-173">8</span></span> | <span data-ttu-id="be38a-174">韓国</span><span class="sxs-lookup"><span data-stu-id="be38a-174">Korea</span></span> |
  | <span data-ttu-id="be38a-175">9 </span><span class="sxs-lookup"><span data-stu-id="be38a-175">9</span></span> | <span data-ttu-id="be38a-176">北米 (カナダを除く)</span><span class="sxs-lookup"><span data-stu-id="be38a-176">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="be38a-177">10 </span><span class="sxs-lookup"><span data-stu-id="be38a-177">10</span></span> | <span data-ttu-id="be38a-178">南アメリカ</span><span class="sxs-lookup"><span data-stu-id="be38a-178">South America</span></span> |
  | <span data-ttu-id="be38a-179">11 </span><span class="sxs-lookup"><span data-stu-id="be38a-179">11</span></span> | <span data-ttu-id="be38a-180">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="be38a-180">South Africa</span></span> |
  | <span data-ttu-id="be38a-181">12 </span><span class="sxs-lookup"><span data-stu-id="be38a-181">12</span></span> | <span data-ttu-id="be38a-182">スイス</span><span class="sxs-lookup"><span data-stu-id="be38a-182">Switzerland</span></span> |
  | <span data-ttu-id="be38a-183">13 </span><span class="sxs-lookup"><span data-stu-id="be38a-183">13</span></span> | <span data-ttu-id="be38a-184">アラブ首長国連邦</span><span class="sxs-lookup"><span data-stu-id="be38a-184">United Arab Emirates</span></span> |
  | <span data-ttu-id="be38a-185">14 </span><span class="sxs-lookup"><span data-stu-id="be38a-185">14</span></span> | <span data-ttu-id="be38a-186">英国</span><span class="sxs-lookup"><span data-stu-id="be38a-186">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="be38a-187">このレポートには、SWIFT コード、クレジット カード番号など、MCCA でサポートされている国際機密情報の種類が常に含まれます。</span><span class="sxs-lookup"><span data-stu-id="be38a-187">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="be38a-188">役割ベースのレポート</span><span class="sxs-lookup"><span data-stu-id="be38a-188">Role-based reporting</span></span>

<span data-ttu-id="be38a-189">また、レポートはロールに基づいてカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="be38a-189">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="be38a-190">次の表に、レポートのセクションにアクセスできるロールを示します。</span><span class="sxs-lookup"><span data-stu-id="be38a-190">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="be38a-191">組織内のその他の役割 (以下の表に記載されていない) は、ツールを実行できない場合や、ツールを実行して最終レポートの情報へのアクセスが制限されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="be38a-191">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="be38a-192">![MCCA - 役割](../media/compliance-manager-mcca-roles.png "MCCA の役割")</span><span class="sxs-lookup"><span data-stu-id="be38a-192">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="be38a-193">例外:</span><span class="sxs-lookup"><span data-stu-id="be38a-193">Exceptions:</span></span>
1. <span data-ttu-id="be38a-194">[Exchange Online で IRM を使用する] セクション以外では、IP のレポートを生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="be38a-194">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="be38a-195">ユーザーは、"Exchange Online に IRM を使用する" セクションとは別に IP のレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="be38a-195">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="be38a-196">ユーザーは、[O365 で通信コンプライアンスを有効にする] セクション以外の IP のレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="be38a-196">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="be38a-197">ユーザーは、[365 年 365 日に監査を有効にする] セクション以外の IP Office生成できない。</span><span class="sxs-lookup"><span data-stu-id="be38a-197">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="be38a-198">ユーザーは、"365 年 365 日に監査を有効にする" セクションOffice IP のレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="be38a-198">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="be38a-199">[ソリューションの概要] セクション</span><span class="sxs-lookup"><span data-stu-id="be38a-199">Solutions Summary section</span></span>

<span data-ttu-id="be38a-200">レポート **の [ソリューション** の概要] セクションには、コンプライアンス の体制を改善するためにコンプライアンス マネージャーで組織が実行できる改善アクションの概要が示されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-200">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="be38a-201">![MCCA - ソリューションの概要](../media/compliance-manager-mcca-solutions.png "MCCA ソリューションの概要画面")</span><span class="sxs-lookup"><span data-stu-id="be38a-201">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="be38a-202">MCCA は、コンプライアンス マネージャーの推奨される改善アクションに対して現在の構成を評価します。</span><span class="sxs-lookup"><span data-stu-id="be38a-202">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="be38a-203">MCCA ツールによって注意が必要と識別された改善アクションについては、このセクションに記載します。</span><span class="sxs-lookup"><span data-stu-id="be38a-203">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="be38a-204">各 Microsoft ソリューションの横には、コンプライアンス マネージャーの改善アクションに対応するアイテムの数を示す色分けされたボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="be38a-204">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="be38a-205">アクションは、次の 3 つの状態に分かれます。</span><span class="sxs-lookup"><span data-stu-id="be38a-205">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="be38a-206">**OK**: 推奨される条件を満たすアクションであり、現時点では注意を必要としません</span><span class="sxs-lookup"><span data-stu-id="be38a-206">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="be38a-207">**改善**: 注意が必要なアクション</span><span class="sxs-lookup"><span data-stu-id="be38a-207">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="be38a-208">**推奨事項**: 注意が必要ないが、ベスト プラクティスをお勧めするアクション</span><span class="sxs-lookup"><span data-stu-id="be38a-208">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="be38a-209">機能強化と推奨事項を表示するボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="be38a-209">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="be38a-210">**改善ステータスのアイテム**</span><span class="sxs-lookup"><span data-stu-id="be38a-210">**Items with the Improvement status**</span></span>

<span data-ttu-id="be38a-211">改善アクションの右側にある **[改善** ] ラベルの横にあるドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="be38a-211">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="be38a-212">現在の設定と推奨される改善アクションに関する簡単な概要と詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-212">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="be38a-213">概要には、コンプライアンス マネージャー、Microsoft 365 コンプライアンス センターの該当するソリューション、関連ドキュメントへの直接リンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="be38a-213">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="be38a-214">[コンプライアンス マネージャー] リンクをクリックすると、まだ実装していないソリューション内のすべての改善アクションのフィルタービューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-214">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="be38a-215">そこから、コンプライアンス スコアを上げ上げするために達成できるポイント数、[](compliance-score-calculation.md)コンプライアンス スコアが適用される評価、適用される規制と認定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="be38a-215">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="be38a-216">DLP には、推奨される機能に基づいて事前に生成された PowerShell スクリプトを提供する修復スクリプト ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="be38a-216">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="be38a-217">PowerShell コンソールに直接コピーして貼り付けできます。</span><span class="sxs-lookup"><span data-stu-id="be38a-217">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="be38a-218">テスト モードで DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="be38a-218">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="be38a-219">**Recommendation 状態のアイテム**</span><span class="sxs-lookup"><span data-stu-id="be38a-219">**Items with Recommendation status**</span></span>

<span data-ttu-id="be38a-220">改善アクションの右側にある **[おすすめ** ] ラベルの横にあるドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="be38a-220">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="be38a-221">改善アクションに関連する組織の現在の Microsoft 365 環境の概要と、推奨されるベスト プラクティスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be38a-221">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="be38a-222">リソース</span><span class="sxs-lookup"><span data-stu-id="be38a-222">Resources</span></span>

<span data-ttu-id="be38a-223">MCCA のインストール、セットアップ、使用の詳細については、GitHub の README の手順を参照してください [(GitHub](https://github.com/OfficeDev/MCCA#overview) アカウントは必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="be38a-223">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="be38a-224">PowerShell の詳細についてはWindows PowerShell [PowerShell](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be38a-224">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="be38a-225">「スタートページ[」もWindows PowerShell。](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="be38a-225">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
