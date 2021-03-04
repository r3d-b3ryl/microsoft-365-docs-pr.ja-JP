---
title: コンプライアンス マネージャー用の Microsoft コンプライアンス構成アナライザー
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
description: Microsoft コンプライアンス構成アナライザーを使用して、Microsoft コンプライアンス マネージャーを使用して迅速に立ち上げ、実行する方法について説明します。
ms.openlocfilehash: 41315dd072e089bd61767181b17dffd5fba88281
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423428"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="ee48b-103">コンプライアンス マネージャー用 Microsoft コンプライアンス構成アナライザー (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ee48b-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="ee48b-104">**この記事では、次の情報を参照してください。** Microsoft コンプライアンス構成アナライザー ツールをインストールして実行して、Microsoft コンプライアンス 管理プログラムをすぐに開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="ee48b-105">Microsoft コンプライアンス構成アナライザー (MCCA) (プレビュー) の概要</span><span class="sxs-lookup"><span data-stu-id="ee48b-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="ee48b-106">Microsoft コンプライアンス構成アナライザー (MCCA) は [、Microsoft](compliance-manager.md)コンプライアンス マネージャーの開始に役立つプレビュー ツールです。</span><span class="sxs-lookup"><span data-stu-id="ee48b-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="ee48b-107">MCCA は、組織の現在の構成をフェッチし、Microsoft 365 推奨ベスト プラクティスに対して検証する PowerShell ベースのユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="ee48b-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="ee48b-108">これらのベスト プラクティスは、データ保護とデータ ガバナンスの主要な規制と標準を含む一連のコントロールに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="ee48b-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="ee48b-109">MCCA を使用すると、コンプライアンス 管理の改善アクションが現在の Microsoft 365 環境に適用される状況をすばやく確認できます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="ee48b-110">MCCA によって識別される各アクションには、コンプライアンス マネージャーへの直接リンクと、修正アクションの実行を開始する適切なソリューションを含む、実装に関する推奨事項が示されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="ee48b-111">MCCA を理解するもう 1 つのリソースは [、GitHub の README の指示にアクセスする方法です](https://github.com/OfficeDev/MCCA#overview)。</span><span class="sxs-lookup"><span data-stu-id="ee48b-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="ee48b-112">このページでは、前提条件に関する詳細な情報を提供し、完全なインストール手順を示します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="ee48b-113">このページにアクセスするには、GitHub アカウントは必要ない。</span><span class="sxs-lookup"><span data-stu-id="ee48b-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="ee48b-114">**可用性**: MCCA は、Office 365 ライセンスと Microsoft 365 ライセンスと米国政府機関コミュニティ (GCC) 中程度および GCC 高い顧客を持つすべての組織で利用できます。DOD のお客様にサービスを拡大する計画が進行中です。</span><span class="sxs-lookup"><span data-stu-id="ee48b-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate and GCC High customers, with plans underway to expand service to DOD customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="ee48b-115">MCCA をインストールしてレポートを実行する</span><span class="sxs-lookup"><span data-stu-id="ee48b-115">Install MCCA and run a report</span></span>

<span data-ttu-id="ee48b-116">MCCA ツールは、次のコマンドを使用Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ee48b-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="ee48b-117">ツールをダウンロードしてインストールしたら、レポートを実行するためにこれらの手順を繰り返す必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="ee48b-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="ee48b-118">MCCA を開くごとに、ログイン資格情報を求め、新しい更新されたレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="ee48b-119">手順 1: インストールWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee48b-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="ee48b-120">まず、PowerShell ギャラリーで使用できる Exchange Online PowerShell モジュール (v2.0.3 以上) が必要です。</span><span class="sxs-lookup"><span data-stu-id="ee48b-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="ee48b-121">[インストール手順を取得します](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)。</span><span class="sxs-lookup"><span data-stu-id="ee48b-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="ee48b-122">手順 2: MCCA をインストールする</span><span class="sxs-lookup"><span data-stu-id="ee48b-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="ee48b-123">MCCA をインストールするには、まず管理者モードで PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="ee48b-124">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ee48b-124">Follow the steps below:</span></span>

1. <span data-ttu-id="ee48b-125">[Windows スタート] **ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="ee48b-126">**「PowerShell」と** 入力し、[**管理者として実行** Windows PowerShellを選択します **。**</span><span class="sxs-lookup"><span data-stu-id="ee48b-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="ee48b-127">コマンド プロンプトで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="ee48b-128">手順 3: レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="ee48b-128">Step 3: Run a report</span></span>

<span data-ttu-id="ee48b-129">MCCA をインストールした後、MCCA を実行してレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="ee48b-130">レポートを実行するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-130">To run a report:</span></span>

1. <span data-ttu-id="ee48b-131">PowerShell を開く</span><span class="sxs-lookup"><span data-stu-id="ee48b-131">Open PowerShell</span></span>
2. <span data-ttu-id="ee48b-132">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```
   <span data-ttu-id="ee48b-133">GCC High のお客様の場合は、レポートを実行するために追加の入力パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee48b-133">If you're a GCC High customer, you'll need to provide an additional input parameter to run the report:</span></span>

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. <span data-ttu-id="ee48b-134">MCCA を実行すると、初期バージョン チェックが実行され、資格情報が要求されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-134">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="ee48b-135">[ユーザー名の入力] プロンプトで、Microsoft 365 アカウントの電子メール アドレスでサインインします (レポートの作成に適格な役割[を表示します](#role-based-reporting))。</span><span class="sxs-lookup"><span data-stu-id="ee48b-135">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="ee48b-136">次に、パスワード プロンプトでパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-136">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="ee48b-137">その後、レポートの生成に約 2 ~ 5 分かかります。</span><span class="sxs-lookup"><span data-stu-id="ee48b-137">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="ee48b-138">完了すると、ブラウザー ウィンドウが開き、HTML レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-138">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="ee48b-139">ツールを実行する度に、資格情報を要求し、新しいレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-139">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="ee48b-140">このレポートは、次のディレクトリにローカルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-140">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="ee48b-141">C:\Users \<username> \AppData\Local\Microsoft\MCCA。</span><span class="sxs-lookup"><span data-stu-id="ee48b-141">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="ee48b-142">このディレクトリから、以前に生成されたレポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-142">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="ee48b-143">レポートについて</span><span class="sxs-lookup"><span data-stu-id="ee48b-143">Understanding your report</span></span>

<span data-ttu-id="ee48b-144">レポートには、生成された日時に基づくデータが反映されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-144">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="ee48b-145">上部のセクションでは、生成された時間、組織名、テナント ID の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-145">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="ee48b-146">位置情報ベースのレポート</span><span class="sxs-lookup"><span data-stu-id="ee48b-146">Geolocation-based reporting</span></span>

<span data-ttu-id="ee48b-147">[ **メモ]** セクションでは、テナントの地理的な場所に基づいてレポートがカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-147">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="ee48b-148">ツールに記載されている推奨事項は、お客様の国または地域に固有の情報です。</span><span class="sxs-lookup"><span data-stu-id="ee48b-148">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="ee48b-149">地理位置情報の選択は、その位置情報に関連する機密情報の種類 (SIT) を評価し、国または地域に合ったレポートを生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-149">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="ee48b-150">テナント内のデータに基づいて地理位置情報を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-150">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="ee48b-151">レポートの位置情報を変更するには、位置情報 (-Geo) 入力パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee48b-151">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="ee48b-152">テナントに適用可能な 1 つ以上の地理的位置を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-152">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="ee48b-153">特定の場所に基づいてレポートを実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ee48b-153">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="ee48b-154">PowerShell を開く</span><span class="sxs-lookup"><span data-stu-id="ee48b-154">Open PowerShell</span></span>
2. <span data-ttu-id="ee48b-155">特定の地域を指定するには、国または地域に対応する下の表の番号を使用してコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-155">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="ee48b-156">複数の数値をコンマで区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-156">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="ee48b-157">たとえば、次のコマンドレットは、ユーザーと日本のユーザー向Asia-Pacific実行します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-157">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="ee48b-158">Input</span><span class="sxs-lookup"><span data-stu-id="ee48b-158">Input</span></span> |  <span data-ttu-id="ee48b-159">国または地域</span><span class="sxs-lookup"><span data-stu-id="ee48b-159">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="ee48b-160">1 </span><span class="sxs-lookup"><span data-stu-id="ee48b-160">1</span></span> | <span data-ttu-id="ee48b-161">アジア太平洋</span><span class="sxs-lookup"><span data-stu-id="ee48b-161">Asia-Pacific</span></span> |
  | <span data-ttu-id="ee48b-162">2 </span><span class="sxs-lookup"><span data-stu-id="ee48b-162">2</span></span> | <span data-ttu-id="ee48b-163">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="ee48b-163">Australia</span></span> |
  | <span data-ttu-id="ee48b-164">3 </span><span class="sxs-lookup"><span data-stu-id="ee48b-164">3</span></span> | <span data-ttu-id="ee48b-165">カナダ</span><span class="sxs-lookup"><span data-stu-id="ee48b-165">Canada</span></span> |
  | <span data-ttu-id="ee48b-166">4 </span><span class="sxs-lookup"><span data-stu-id="ee48b-166">4</span></span> | <span data-ttu-id="ee48b-167">ヨーロッパ (フランスを除く) / 中東 / アフリカ</span><span class="sxs-lookup"><span data-stu-id="ee48b-167">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="ee48b-168">5 </span><span class="sxs-lookup"><span data-stu-id="ee48b-168">5</span></span> | <span data-ttu-id="ee48b-169">フランス</span><span class="sxs-lookup"><span data-stu-id="ee48b-169">France</span></span> |
  | <span data-ttu-id="ee48b-170">6 </span><span class="sxs-lookup"><span data-stu-id="ee48b-170">6</span></span> | <span data-ttu-id="ee48b-171">インド</span><span class="sxs-lookup"><span data-stu-id="ee48b-171">India</span></span> |
  | <span data-ttu-id="ee48b-172">7 </span><span class="sxs-lookup"><span data-stu-id="ee48b-172">7</span></span> | <span data-ttu-id="ee48b-173">日本</span><span class="sxs-lookup"><span data-stu-id="ee48b-173">Japan</span></span> |
  | <span data-ttu-id="ee48b-174">8 </span><span class="sxs-lookup"><span data-stu-id="ee48b-174">8</span></span> | <span data-ttu-id="ee48b-175">韓国</span><span class="sxs-lookup"><span data-stu-id="ee48b-175">Korea</span></span> |
  | <span data-ttu-id="ee48b-176">9 </span><span class="sxs-lookup"><span data-stu-id="ee48b-176">9</span></span> | <span data-ttu-id="ee48b-177">北アメリカ (カナダを除く)</span><span class="sxs-lookup"><span data-stu-id="ee48b-177">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="ee48b-178">10  </span><span class="sxs-lookup"><span data-stu-id="ee48b-178">10</span></span> | <span data-ttu-id="ee48b-179">南アメリカ</span><span class="sxs-lookup"><span data-stu-id="ee48b-179">South America</span></span> |
  | <span data-ttu-id="ee48b-180">11</span><span class="sxs-lookup"><span data-stu-id="ee48b-180">11</span></span> | <span data-ttu-id="ee48b-181">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="ee48b-181">South Africa</span></span> |
  | <span data-ttu-id="ee48b-182">12 </span><span class="sxs-lookup"><span data-stu-id="ee48b-182">12</span></span> | <span data-ttu-id="ee48b-183">スイス</span><span class="sxs-lookup"><span data-stu-id="ee48b-183">Switzerland</span></span> |
  | <span data-ttu-id="ee48b-184">13 </span><span class="sxs-lookup"><span data-stu-id="ee48b-184">13</span></span> | <span data-ttu-id="ee48b-185">アラブ首長国連邦</span><span class="sxs-lookup"><span data-stu-id="ee48b-185">United Arab Emirates</span></span> |
  | <span data-ttu-id="ee48b-186">14 </span><span class="sxs-lookup"><span data-stu-id="ee48b-186">14</span></span> | <span data-ttu-id="ee48b-187">英国</span><span class="sxs-lookup"><span data-stu-id="ee48b-187">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="ee48b-188">このレポートには、SWIFT コード、クレジット カード番号など、MCCA でサポートされる国際的な機密情報の種類が常に含まれます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-188">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="ee48b-189">役割ベースのレポート</span><span class="sxs-lookup"><span data-stu-id="ee48b-189">Role-based reporting</span></span>

<span data-ttu-id="ee48b-190">また、レポートは役割に基づいてカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-190">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="ee48b-191">次の表に、レポートのセクションにアクセスできる役割を示します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-191">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="ee48b-192">組織内の他の役割 (下の表に記載されていない) は、ツールを実行できないか、ツールを実行し、最終レポートの情報へのアクセスが制限されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ee48b-192">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="ee48b-193">![MCCA - ロール](../media/compliance-manager-mcca-roles.png "MCCA の役割")</span><span class="sxs-lookup"><span data-stu-id="ee48b-193">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="ee48b-194">例外:</span><span class="sxs-lookup"><span data-stu-id="ee48b-194">Exceptions:</span></span>
1. <span data-ttu-id="ee48b-195">[Exchange Online で IRM を使用する] セクション以外では、IP のレポートを生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ee48b-195">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="ee48b-196">ユーザーは、[Exchange Online で IRM を使用する] セクション以外の IP のレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-196">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="ee48b-197">ユーザーは、[O365 で通信コンプライアンスを有効にする] セクションとは別に、IP のレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-197">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="ee48b-198">ユーザーは、[365 で監査を有効にする] セクション以外の IP Office生成できない。</span><span class="sxs-lookup"><span data-stu-id="ee48b-198">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="ee48b-199">ユーザーは、[365 で監査を有効にする] セクションとは別に、IP Office生成できます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-199">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="ee48b-200">[ソリューションの概要] セクション</span><span class="sxs-lookup"><span data-stu-id="ee48b-200">Solutions Summary section</span></span>

<span data-ttu-id="ee48b-201">レポート **の [ソリューションの** 概要] セクションには、コンプライアンス 体制の向上に役立つコンプライアンス マネージャーで組織が実行できる改善アクションの概要が示されています。</span><span class="sxs-lookup"><span data-stu-id="ee48b-201">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="ee48b-202">![MCCA - ソリューションの概要](../media/compliance-manager-mcca-solutions.png "MCCA ソリューションの概要画面")</span><span class="sxs-lookup"><span data-stu-id="ee48b-202">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="ee48b-203">MCCA は、コンプライアンス マネージャーで推奨される改善アクションに対して現在の構成を評価します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-203">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="ee48b-204">MCCA ツールで注意が必要と識別される改善アクションは、このセクションに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-204">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="ee48b-205">各 Microsoft ソリューションの横には、コンプライアンス マネージャーの改善アクションに対応するアイテムの数を示す色分けされたボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="ee48b-205">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="ee48b-206">アクションは、次の 3 つの状態に分割されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-206">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="ee48b-207">**OK**: 推奨される条件を満たすアクションで、現時点では注意が必要ない</span><span class="sxs-lookup"><span data-stu-id="ee48b-207">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="ee48b-208">**改善**: 注意が必要なアクション</span><span class="sxs-lookup"><span data-stu-id="ee48b-208">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="ee48b-209">**推奨事項**: 注意を必要としませんが、ベスト プラクティスを推奨するアクション</span><span class="sxs-lookup"><span data-stu-id="ee48b-209">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="ee48b-210">ボックスを選択して、改善点と推奨事項を表示します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-210">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="ee48b-211">**[改善] 状態のアイテム**</span><span class="sxs-lookup"><span data-stu-id="ee48b-211">**Items with the Improvement status**</span></span>

<span data-ttu-id="ee48b-212">改善アクションの右側にある **[改善** ] ラベルの横にあるドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-212">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="ee48b-213">現在の設定と推奨される改善アクションに関する簡単な概要と詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-213">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="ee48b-214">概要には、コンプライアンス マネージャーへの直接リンク、Microsoft 365 コンプライアンス センターの該当するソリューション、および関連するドキュメントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-214">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="ee48b-215">[コンプライアンス マネージャー] リンクをクリックすると、まだ実装していないソリューション内のすべての改善アクションのフィルタービューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-215">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="ee48b-216">そこから、コンプライアンス スコアを上げ、適用する評価、適用される規制[](compliance-score-calculation.md)と認定を増やして得るポイントの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-216">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="ee48b-217">DLP の場合、推奨される情報に基づいて事前に生成された PowerShell スクリプトを提供する [修復スクリプト] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="ee48b-217">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="ee48b-218">PowerShell コンソールにコピーして直接貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-218">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="ee48b-219">テスト モードで DLP ポリシーを作成します</span><span class="sxs-lookup"><span data-stu-id="ee48b-219">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="ee48b-220">**推奨事項の状態を持つアイテム**</span><span class="sxs-lookup"><span data-stu-id="ee48b-220">**Items with Recommendation status**</span></span>

<span data-ttu-id="ee48b-221">改善アクションの右側にある **[おすすめ** ] ラベルの横にあるドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ee48b-221">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="ee48b-222">組織の現在の Microsoft 365 環境の概要と、推奨されるベスト プラクティスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee48b-222">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="ee48b-223">リソース</span><span class="sxs-lookup"><span data-stu-id="ee48b-223">Resources</span></span>

<span data-ttu-id="ee48b-224">MCCA のインストール、セットアップ、および使用の詳細については、GitHub の README の手順 [(GitHub](https://github.com/OfficeDev/MCCA#overview) アカウントは必要ありません) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee48b-224">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="ee48b-225">詳細については、「PowerShell Windows PowerShell [の使い方」を参照してください](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="ee48b-225">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="ee48b-226">[「Starting Windows PowerShell」も参照してください](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="ee48b-226">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
