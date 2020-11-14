---
title: コンプライアンスマネージャーのための Microsoft コンプライアンス構成アナライザー
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
description: Microsoft コンプライアンス構成アナライザーを使用して Microsoft コンプライアンスマネージャーをすばやく開始して実行する方法について説明します。
ms.openlocfilehash: 1f7d987262a7d390cb9efe2162ae9be9f56c8757
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49072006"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager"></a><span data-ttu-id="fea83-103">コンプライアンスマネージャーのための Microsoft コンプライアンス構成アナライザー</span><span class="sxs-lookup"><span data-stu-id="fea83-103">Microsoft Compliance Configuration Analyzer for Compliance Manager</span></span>

<span data-ttu-id="fea83-104">**この記事の内容** Microsoft コンプライアンス構成アナライザーツールをインストールおよび実行して、Microsoft コンプライアンスマネージャーをすばやく開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fea83-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-overview"></a><span data-ttu-id="fea83-105">Microsoft コンプライアンス構成アナライザー (MCCA) の概要</span><span class="sxs-lookup"><span data-stu-id="fea83-105">Microsoft Compliance Configuration Analyzer (MCCA) overview</span></span>

<span data-ttu-id="fea83-106">Microsoft コンプライアンス構成アナライザー (MCCA) は、 [Microsoft コンプライアンスマネージャー](compliance-manager.md)を使い始めるときに役立つツールです。</span><span class="sxs-lookup"><span data-stu-id="fea83-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="fea83-107">MCCA は、組織の現在の構成を取得し、Microsoft 365 の推奨されるベストプラクティスに照らして検証する PowerShell ベースのユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="fea83-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="fea83-108">これらのベストプラクティスは、データ保護とデータガバナンスに関する主要な規制と基準を含む一連のコントロールに基づいています。</span><span class="sxs-lookup"><span data-stu-id="fea83-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="fea83-109">MCCA は、コンプライアンスマネージャーのどの改善アクションが現在の Microsoft 365 環境に適用されるかをすばやく確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fea83-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="fea83-110">MCCA によって識別されるアクションごとに、実装の推奨事項、コンプライアンスマネージャーへの直接リンク、是正措置を開始するための適切なソリューションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="fea83-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="fea83-111">MCCA を理解するためのその他のリソースについては、 [GitHub の README の手順](https://github.com/OfficeDev/MCCA#overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fea83-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="fea83-112">このページでは、前提条件に関する詳細情報を提供し、完全なインストール手順を示します。</span><span class="sxs-lookup"><span data-stu-id="fea83-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="fea83-113">このページにアクセスするには、GitHub アカウントは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="fea83-113">You don’t need a GitHub account to access this page.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="fea83-114">MCCA をインストールしてレポートを実行する</span><span class="sxs-lookup"><span data-stu-id="fea83-114">Install MCCA and run a report</span></span>

<span data-ttu-id="fea83-115">MCCA ツールは、Windows PowerShell を使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="fea83-115">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="fea83-116">ツールをダウンロードしてインストールした後は、レポートを実行するためにこれらの手順を繰り返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fea83-116">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="fea83-117">MCCA を開くたびに、ログイン資格情報の入力が求められ、更新された新しいレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="fea83-117">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="fea83-118">手順 1: Windows PowerShell をインストールする</span><span class="sxs-lookup"><span data-stu-id="fea83-118">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="fea83-119">開始するには、PowerShell ギャラリーで利用できる Exchange Online PowerShell モジュール (v 2.0.3 以上) が必要です。</span><span class="sxs-lookup"><span data-stu-id="fea83-119">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="fea83-120">[インストール手順を取得](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)します。</span><span class="sxs-lookup"><span data-stu-id="fea83-120">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="fea83-121">手順 2: MCCA をインストールする</span><span class="sxs-lookup"><span data-stu-id="fea83-121">Step 2: Install MCCA</span></span>

<span data-ttu-id="fea83-122">MCCA をインストールするには、管理者モードで PowerShell を使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="fea83-122">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="fea83-123">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fea83-123">Follow the steps below:</span></span>

1. <span data-ttu-id="fea83-124">Windows の [ **スタート** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="fea83-124">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="fea83-125">「 **Powershell** 」と入力し、[ **Windows PowerShell** ] を右クリックし、[ **管理者として実行** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fea83-125">Type **PowerShell** , right-click on **Windows PowerShell** , then select **Run as administrator**.</span></span>
1. <span data-ttu-id="fea83-126">コマンドプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fea83-126">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="fea83-127">手順 3: レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="fea83-127">Step 3: Run a report</span></span>

<span data-ttu-id="fea83-128">MCCA をインストールした後、MCCA を実行し、レポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="fea83-128">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="fea83-129">レポートを実行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fea83-129">To run a report:</span></span>

1. <span data-ttu-id="fea83-130">PowerShell を開く</span><span class="sxs-lookup"><span data-stu-id="fea83-130">Open PowerShell</span></span>
2. <span data-ttu-id="fea83-131">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fea83-131">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```
3. <span data-ttu-id="fea83-132">MCCA を実行すると、最初のバージョンチェックが行われ、資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="fea83-132">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="fea83-133">[ユーザー名の入力を求める] プロンプトで、Microsoft 365 アカウントの電子メールアドレスを使用してサインインします ([レポートを作成するのに適した役割を表示](#role-based-reporting)します)。</span><span class="sxs-lookup"><span data-stu-id="fea83-133">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="fea83-134">パスワードプロンプトで、パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="fea83-134">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="fea83-135">レポートの生成には約2-5 分かかります。</span><span class="sxs-lookup"><span data-stu-id="fea83-135">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="fea83-136">完了すると、ブラウザーウィンドウが開き、HTML レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fea83-136">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="fea83-137">ツールを実行するたびに、資格情報の入力が求められ、新しいレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="fea83-137">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="fea83-138">このレポートは、ローカルの次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="fea83-138">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="fea83-139">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="fea83-139">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="fea83-140">このディレクトリから、以前に生成されたレポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fea83-140">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="fea83-141">レポートについて</span><span class="sxs-lookup"><span data-stu-id="fea83-141">Understanding your report</span></span>

<span data-ttu-id="fea83-142">レポートには、生成された日付と時刻に基づいてデータが反映されます。</span><span class="sxs-lookup"><span data-stu-id="fea83-142">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="fea83-143">上部のセクションでは、生成された日時、組織名、およびテナント ID の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="fea83-143">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="fea83-144">地理位置情報に基づくレポート</span><span class="sxs-lookup"><span data-stu-id="fea83-144">Geolocation-based reporting</span></span>

<span data-ttu-id="fea83-145">[ **メモ** ] セクションは、テナントの地理的な場所に基づいてレポートがカスタマイズされていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="fea83-145">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="fea83-146">このツールには、お住まいの国または地域に固有の推奨事項が記載されています。</span><span class="sxs-lookup"><span data-stu-id="fea83-146">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="fea83-147">地理位置情報の選択を使用して、その地理位置情報に関連する機密情報の種類 (つまり、) を評価し、国または地域に合わせたレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="fea83-147">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="fea83-148">テナント内のデータに基づいて、geolocations を選択します。</span><span class="sxs-lookup"><span data-stu-id="fea83-148">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="fea83-149">レポートの場所情報を変更するには、地理位置情報 (-Geo) 入力パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fea83-149">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="fea83-150">テナントに適用する1つまたは複数の geolocations を選択できます。</span><span class="sxs-lookup"><span data-stu-id="fea83-150">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="fea83-151">特定の場所に基づいてレポートを実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fea83-151">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="fea83-152">PowerShell を開く</span><span class="sxs-lookup"><span data-stu-id="fea83-152">Open PowerShell</span></span>
2. <span data-ttu-id="fea83-153">特定の地域を指定するには、次の表の番号を使用して、国または地域に対応するコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fea83-153">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="fea83-154">複数の数値を入力するには、コンマで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="fea83-154">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="fea83-155">たとえば、次のコマンドレットでは、Asia-Pacific と日本のカスタマイズされたレポートを実行します。</span><span class="sxs-lookup"><span data-stu-id="fea83-155">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="fea83-156">Input</span><span class="sxs-lookup"><span data-stu-id="fea83-156">Input</span></span> |  <span data-ttu-id="fea83-157">国または地域</span><span class="sxs-lookup"><span data-stu-id="fea83-157">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="fea83-158">1 </span><span class="sxs-lookup"><span data-stu-id="fea83-158">1</span></span> | <span data-ttu-id="fea83-159">アジア太平洋</span><span class="sxs-lookup"><span data-stu-id="fea83-159">Asia-Pacific</span></span> |
  | <span data-ttu-id="fea83-160">2 </span><span class="sxs-lookup"><span data-stu-id="fea83-160">2</span></span> | <span data-ttu-id="fea83-161">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="fea83-161">Australia</span></span> |
  | <span data-ttu-id="fea83-162">1/3</span><span class="sxs-lookup"><span data-stu-id="fea83-162">3</span></span> | <span data-ttu-id="fea83-163">カナダ</span><span class="sxs-lookup"><span data-stu-id="fea83-163">Canada</span></span> |
  | <span data-ttu-id="fea83-164">4 </span><span class="sxs-lookup"><span data-stu-id="fea83-164">4</span></span> | <span data-ttu-id="fea83-165">ヨーロッパ (フランスを除く)/中東/アフリカ</span><span class="sxs-lookup"><span data-stu-id="fea83-165">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="fea83-166">5 </span><span class="sxs-lookup"><span data-stu-id="fea83-166">5</span></span> | <span data-ttu-id="fea83-167">フランス</span><span class="sxs-lookup"><span data-stu-id="fea83-167">France</span></span> |
  | <span data-ttu-id="fea83-168">6 </span><span class="sxs-lookup"><span data-stu-id="fea83-168">6</span></span> | <span data-ttu-id="fea83-169">インド</span><span class="sxs-lookup"><span data-stu-id="fea83-169">India</span></span> |
  | <span data-ttu-id="fea83-170">7 </span><span class="sxs-lookup"><span data-stu-id="fea83-170">7</span></span> | <span data-ttu-id="fea83-171">日本</span><span class="sxs-lookup"><span data-stu-id="fea83-171">Japan</span></span> |
  | <span data-ttu-id="fea83-172">8 </span><span class="sxs-lookup"><span data-stu-id="fea83-172">8</span></span> | <span data-ttu-id="fea83-173">韓国</span><span class="sxs-lookup"><span data-stu-id="fea83-173">Korea</span></span> |
  | <span data-ttu-id="fea83-174">9 </span><span class="sxs-lookup"><span data-stu-id="fea83-174">9</span></span> | <span data-ttu-id="fea83-175">北米 (カナダを除く)</span><span class="sxs-lookup"><span data-stu-id="fea83-175">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="fea83-176">10  </span><span class="sxs-lookup"><span data-stu-id="fea83-176">10</span></span> | <span data-ttu-id="fea83-177">南アメリカ</span><span class="sxs-lookup"><span data-stu-id="fea83-177">South America</span></span> |
  | <span data-ttu-id="fea83-178">11 </span><span class="sxs-lookup"><span data-stu-id="fea83-178">11</span></span> | <span data-ttu-id="fea83-179">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="fea83-179">South Africa</span></span> |
  | <span data-ttu-id="fea83-180">12 </span><span class="sxs-lookup"><span data-stu-id="fea83-180">12</span></span> | <span data-ttu-id="fea83-181">スイス</span><span class="sxs-lookup"><span data-stu-id="fea83-181">Switzerland</span></span> |
  | <span data-ttu-id="fea83-182">13 </span><span class="sxs-lookup"><span data-stu-id="fea83-182">13</span></span> | <span data-ttu-id="fea83-183">アラブ首長国連邦</span><span class="sxs-lookup"><span data-stu-id="fea83-183">United Arab Emirates</span></span> |
  | <span data-ttu-id="fea83-184">14 </span><span class="sxs-lookup"><span data-stu-id="fea83-184">14</span></span> | <span data-ttu-id="fea83-185">英国</span><span class="sxs-lookup"><span data-stu-id="fea83-185">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="fea83-186">このレポートには、SWIFT コード、クレジットカード番号などの、MCCA がサポートする国際的な機密情報の種類が常に含まれています。</span><span class="sxs-lookup"><span data-stu-id="fea83-186">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="fea83-187">役割に基づくレポート</span><span class="sxs-lookup"><span data-stu-id="fea83-187">Role-based reporting</span></span>

<span data-ttu-id="fea83-188">また、レポートは自分の役割に基づいてカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="fea83-188">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="fea83-189">下の表は、どの役割がレポートのどのセクションにアクセスできるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="fea83-189">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="fea83-190">組織内のその他の役割 (以下の表に記載されていません) は、ツールを実行できない可能性があります。また、ツールを実行して、最終レポートの情報へのアクセスに制限を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="fea83-190">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="fea83-191">![MCCA-役割](../media/compliance-manager-mcca-roles.png "MCCA の役割")</span><span class="sxs-lookup"><span data-stu-id="fea83-191">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="fea83-192">例外:</span><span class="sxs-lookup"><span data-stu-id="fea83-192">Exceptions:</span></span>
1. <span data-ttu-id="fea83-193">ユーザーは、「Exchange Online で IRM を使用する」セクションとは別に IP のレポートを生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="fea83-193">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="fea83-194">ユーザーは、「Exchange Online で IRM を使用する」セクションとは別に IP のレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="fea83-194">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="fea83-195">ユーザーは、「O365 での通信のコンプライアンスを有効にする」セクションとは別に IP のレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="fea83-195">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="fea83-196">ユーザーは、「Office の監査を有効にする365」セクションとは別に IP のレポートを生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="fea83-196">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="fea83-197">ユーザーは、「Office の監査を有効にする365」セクションとは別に IP のレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="fea83-197">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="fea83-198">ソリューションの概要セクション</span><span class="sxs-lookup"><span data-stu-id="fea83-198">Solutions Summary section</span></span>

<span data-ttu-id="fea83-199">このレポートの「 **ソリューションの概要** 」セクションには、コンプライアンスマネージャーによってコンプライアンスの状況を改善するために組織が実施できる改善アクションの概要が示されています。</span><span class="sxs-lookup"><span data-stu-id="fea83-199">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="fea83-200">![MCCA-ソリューションの概要](../media/compliance-manager-mcca-solutions.png "MCCA ソリューションの概要画面")</span><span class="sxs-lookup"><span data-stu-id="fea83-200">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="fea83-201">MCCA は、コンプライアンスマネージャーの推奨される改善アクションに対して現在の構成を評価します。</span><span class="sxs-lookup"><span data-stu-id="fea83-201">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="fea83-202">このセクションでは、MCCA ツールによって特定された改善アクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fea83-202">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="fea83-203">各 Microsoft ソリューションの横に、コンプライアンスマネージャーの向上アクションに対応する項目の数を示す色分けされたボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="fea83-203">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="fea83-204">アクションは、次の3つの状態状態に分類されます。</span><span class="sxs-lookup"><span data-stu-id="fea83-204">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="fea83-205">**OK** : この時点で、推奨される条件を満たし、注意を必要としないアクション</span><span class="sxs-lookup"><span data-stu-id="fea83-205">**OK** : the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="fea83-206">**向上** : 注意が必要な操作</span><span class="sxs-lookup"><span data-stu-id="fea83-206">**Improvement** : actions that need attention</span></span>
- <span data-ttu-id="fea83-207">**推奨事項** : 注意を要することはありませんが、ベストプラクティスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fea83-207">**Recommendation** : actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="fea83-208">改善と推奨事項を表示するボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="fea83-208">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="fea83-209">**向上の状態を持つアイテム**</span><span class="sxs-lookup"><span data-stu-id="fea83-209">**Items with the Improvement status**</span></span>

<span data-ttu-id="fea83-210">向上アクションの右側にある **改善** ラベルの横にあるドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="fea83-210">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="fea83-211">現在の設定と推奨される改善アクションについての簡単な概要と詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fea83-211">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="fea83-212">概要には、コンプライアンスマネージャーへの直接リンク、Microsoft 365 コンプライアンスセンターの該当するソリューション、関連ドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fea83-212">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="fea83-213">[コンプライアンスマネージャー] リンクをクリックすると、そのソリューション内でまだ実装されていないすべての改善アクションがフィルター処理されたビューに移動します。</span><span class="sxs-lookup"><span data-stu-id="fea83-213">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="fea83-214">そこから、 [コンプライアンススコア](compliance-score-calculation.md)を増やすために達成できるポイント数と、適用される評価、適用される規制、認定資格を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fea83-214">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="fea83-215">DLP では、推奨事項に基づいて事前生成された PowerShell スクリプトを提供する **修復スクリプト** ボタンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="fea83-215">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="fea83-216">PowerShell コンソールに直接コピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="fea83-216">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="fea83-217">テストモードで DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fea83-217">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="fea83-218">**推奨事項の状態のアイテム**</span><span class="sxs-lookup"><span data-stu-id="fea83-218">**Items with Recommendation status**</span></span>

<span data-ttu-id="fea83-219">[改善] アクションの右側にある [ **推奨事項** ] ラベルの横にあるドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="fea83-219">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="fea83-220">改善アクションに関連した、組織の現在の Microsoft 365 環境の概要と、推奨されるベストプラクティスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fea83-220">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="fea83-221">リソース</span><span class="sxs-lookup"><span data-stu-id="fea83-221">Resources</span></span>

<span data-ttu-id="fea83-222">MCCA のインストール、セットアップ、および使用の詳細については、 [github の README 指示](https://github.com/OfficeDev/MCCA#overview) を参照してください (github アカウントは必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="fea83-222">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="fea83-223">Windows PowerShell の詳細については、「 [PowerShell ドキュメントの使用方法](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)」を開始してください。</span><span class="sxs-lookup"><span data-stu-id="fea83-223">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="fea83-224">「 [Windows PowerShell を起動](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)する」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="fea83-224">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
