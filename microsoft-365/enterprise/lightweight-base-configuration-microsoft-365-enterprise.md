---
title: 軽量な基本構成
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: このテスト ラボ ガイドを使用して、Microsoft 365 Enterprise をテストするための軽量なテスト環境を作成します。
ms.openlocfilehash: 4e90cc01cb37664f3084daf7295e9d59052809af
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633345"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="7e330-103">軽量な基本構成</span><span class="sxs-lookup"><span data-stu-id="7e330-103">The lightweight base configuration</span></span>

<span data-ttu-id="7e330-104">*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="7e330-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="7e330-105">この記事は、Microsoft 365 E5 サブスクリプションと、Windows 10 Enterprise を実行しているコンピューターを使用して、簡略化された環境を作成する詳細な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="7e330-105">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![軽量な Microsoft 365 Enterprise テスト環境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="7e330-107">作成された環境を使用して、[Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) のフィーチャーと機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="7e330-107">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="7e330-109">[ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7e330-109">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="7e330-110">フェーズ 1: Office 365 E5 サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="7e330-110">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="7e330-111">まず、Office 365 E5 試用版サブスクリプションを使用して、Microsoft 365 E5 サブスクリプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="7e330-111">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="7e330-112">Office 365 E5 試用版サブスクリプションを開始するには、最初に、架空の会社名と新しい Microsoft アカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="7e330-112">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="7e330-p101">この会社名には、会社名 Contoso のバリエーションを使用するようお勧めします (必須ではありません)。Contoso は、Microsoft のサンプル コンテンツで使用される架空の会社名です。ここに架空の会社名を記録してください:</span><span class="sxs-lookup"><span data-stu-id="7e330-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![線](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="7e330-p102">新しい Microsoft アカウントにサインアップするには、[https://outlook.com](https://outlook.com) に移動して、新しい電子メール アカウントとアドレスでアカウントを作成します。このアカウントを使用して、Office 365 にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="7e330-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="7e330-118">ここに新しいアカウントの姓名を記録してください:</span><span class="sxs-lookup"><span data-stu-id="7e330-118">Record the first and last name of your new account here:</span></span> ![線](../media/Common-Images/TableLine.png)
    
  - <span data-ttu-id="7e330-120">新しいメール アカウント アドレスをここに記録します。</span><span class="sxs-lookup"><span data-stu-id="7e330-120">Record the new email account address here:</span></span> ![線](../media/Common-Images/TableLine.png)<span data-ttu-id="7e330-122">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="7e330-122">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="7e330-123">Office 365 E5 試用版サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="7e330-123">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="7e330-124">コンピューターでインターネット ブラウザーを開き、[https://aka.ms/e5trial](https://aka.ms/e5trial) に移動します。</span><span class="sxs-lookup"><span data-stu-id="7e330-124">Open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="7e330-125">「**Office 365 E5 をお選び頂き、ありがとうございます**」ページで、手順 1 の新しいメール アカウントのアドレスを明記します。</span><span class="sxs-lookup"><span data-stu-id="7e330-125">On the **Thank you for choosing Office 365 E5** page, specify, your new email account address in step 1.</span></span>
3. <span data-ttu-id="7e330-126">試用版サブスクリプション プロセスの手順 2 で、必要な情報を入力して、検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e330-126">In step 2 of the trail subscription process, type the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="7e330-127">手順 3 では、組織名を入力して、サブスクリプション用の全体管理者になるアカウント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e330-127">In step 3, type an organization name and then an account name that will be the global admin for the subscription.</span></span> 
5. <span data-ttu-id="7e330-128">手順 4 では、ここにサインイン ページを記録します (選択してコピー):</span><span class="sxs-lookup"><span data-stu-id="7e330-128">For step 4, record the sign-in page here (select and copy):</span></span> ![線](../media/Common-Images/TableLine.png) 
6. <span data-ttu-id="7e330-130">ここにユーザー ID を記録します: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7e330-130">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="7e330-131">入力したパスワードを安全な場所に記録してください。</span><span class="sxs-lookup"><span data-stu-id="7e330-131">Record the password that you typed in a secure location.</span></span>
   <span data-ttu-id="7e330-132">この値を**Office 365 全体管理者名**と呼ぶことにします。</span><span class="sxs-lookup"><span data-stu-id="7e330-132">This value will be referred to as the **Office 365 global administrator name**.</span></span>
8. <span data-ttu-id="7e330-133">[**セットアップに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-133">Click **Go to Setup**.</span></span>
9. <span data-ttu-id="7e330-134">Office 365 E5 のセットアップで、**メールとサインイン用に組織の .onmicrosoft.com* を [* 引き続き続行する**] をクリックして、[**終了して後で続行する\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-134">In Office 365 E5 Setup, click **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then click **Exit and continue later**.</span></span>

<span data-ttu-id="7e330-135">Microsoft 365 管理センターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e330-135">You should see the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="7e330-136">現在お持ちの有料サブスクリプションとは別の Azure AD テナントをテスト環境で保持できるように、Office 365 の試用版サブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e330-136">We have you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="7e330-137">このように分離することにより、運用サブスクリプションに影響を与えることなく、テスト テナントでのユーザーとグループの追加と削除が可能になります。</span><span class="sxs-lookup"><span data-stu-id="7e330-137">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="7e330-138">フェーズ 2: Office 365 試用版サブスクリプションを構成する</span><span class="sxs-lookup"><span data-stu-id="7e330-138">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="7e330-139">このフェーズでは、追加のユーザーで Office 365 のサブスクリプションを構成し、Office 365 E5 ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7e330-139">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="7e330-140">「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)」の手順を使用して、コンピューターから Azure Active Directory PowerShell for Graph モジュールで Office 365 のサブスクリプションに接続します。</span><span class="sxs-lookup"><span data-stu-id="7e330-140">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from your computer.</span></span>
    
<span data-ttu-id="7e330-141">**[Windows PowerShell 資格情報の要求]** ダイアログ ボックスで、Office 365 全体管理者名 (例: jdoe@contosotoycompany.onmicrosoft.com) およびパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7e330-141">In the **Windows PowerShell Credential Request** dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="7e330-142">組織名 (例: contosotoycompany)、所属地域に該当する 2 文字の国別コード、共通のアカウント パスワードを入力して、PowerShellのプロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e330-142">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="7e330-143">ここで共通のパスワードを使用するのは、自動化およびテスト環境の構成を容易にするためです。</span><span class="sxs-lookup"><span data-stu-id="7e330-143">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="7e330-144">運用環境のサブスクリプションは避けるように強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e330-144">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="7e330-145">将来の参照のために重要な情報を記録する</span><span class="sxs-lookup"><span data-stu-id="7e330-145">Record key information for future reference</span></span>

<span data-ttu-id="7e330-146">この記事を印刷しておき、30 日間の Office 365 試用版サブスクリプションの終了後にこの環境で必要になる特定の情報を記録しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e330-146">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="7e330-147">試用版サブスクリプションは、追加で 30 日間まで簡単に延長できます。</span><span class="sxs-lookup"><span data-stu-id="7e330-147">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="7e330-148">永続的なテスト環境の場合は、別個の Azure AD テナントと少数のライセンスを使用して、新しい有料サブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e330-148">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="7e330-149">これらの値を記録する:</span><span class="sxs-lookup"><span data-stu-id="7e330-149">Record these values:</span></span>
  
- <span data-ttu-id="7e330-150">Office 365 グローバル管理者名:</span><span class="sxs-lookup"><span data-stu-id="7e330-150">Office 365 global administrator name:</span></span> ![線](../media/Common-Images/TableLine.png)<span data-ttu-id="7e330-152">.onmicrosoft.com (フェーズ 1 のステップ 6 から)</span><span class="sxs-lookup"><span data-stu-id="7e330-152">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="7e330-153">このアカウントのパスワードも安全な場所に記録してください。</span><span class="sxs-lookup"><span data-stu-id="7e330-153">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="7e330-154">試用版サブスクリプションの組織名:</span><span class="sxs-lookup"><span data-stu-id="7e330-154">Your trial subscription organization name:</span></span> ![線](../media/Common-Images/TableLine.png) <span data-ttu-id="7e330-156">(フェーズ 1 のステップ 4 から)</span><span class="sxs-lookup"><span data-stu-id="7e330-156">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="7e330-157">User 2、User 3、User 4、および User 5 のアカウントを一覧表示するには、次に示すコマンドを Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="7e330-157">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="7e330-158">ここにアカウント名を記録してください:</span><span class="sxs-lookup"><span data-stu-id="7e330-158">Record the account names here:</span></span>
    
  - <span data-ttu-id="7e330-159">ユーザー 2 アカウント名: user2@</span><span class="sxs-lookup"><span data-stu-id="7e330-159">User 2 account name: user2@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="7e330-161">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7e330-161">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="7e330-162">ユーザー 3 アカウント名: user3@</span><span class="sxs-lookup"><span data-stu-id="7e330-162">User 3 account name: user3@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="7e330-164">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7e330-164">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="7e330-165">ユーザー 4 アカウント名: user4@</span><span class="sxs-lookup"><span data-stu-id="7e330-165">User 4 account name: user4@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="7e330-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7e330-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="7e330-168">ユーザー 5 アカウント名: user5@</span><span class="sxs-lookup"><span data-stu-id="7e330-168">User 5 account name: user5@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="7e330-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7e330-170">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="7e330-171">これらのアカウントの共通パスワードも安全な場所に記録してください。</span><span class="sxs-lookup"><span data-stu-id="7e330-171">Also record the common password for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="7e330-172">Office 365 テスト環境を使用する</span><span class="sxs-lookup"><span data-stu-id="7e330-172">Using an Office 365 test environment</span></span>

<span data-ttu-id="7e330-173">Office 365 のテスト環境だけが必要な場合は、ここで終了します。</span><span class="sxs-lookup"><span data-stu-id="7e330-173">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="7e330-174">Office 365 と Microsoft 365 の両方に適用される追加のテスト ラボ ガイドについては、「[Microsoft 365 エンタープライズ テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e330-174">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="7e330-175">フェーズ 3: Microsoft 365 E5 の試用版サブスクリプションを追加する</span><span class="sxs-lookup"><span data-stu-id="7e330-175">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="7e330-176">このフェーズでは、Microsoft 365 E5 試用版サブスクリプションにサインアップして、Office 365 E5 試用版サブスクリプションと同じ組織に追加します。</span><span class="sxs-lookup"><span data-stu-id="7e330-176">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="7e330-177">まず、Microsoft 365 E5 試用版サブスクリプションを追加して、新しい Microsoft 365 ライセンスを全体管理者アカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7e330-177">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="7e330-178">インターネット ブラウザーのプライベート インスタンスで、全体管理者アカウントの資格情報を使用して、Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7e330-178">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="7e330-179">**[Microsoft 365 管理センター]** ページの左側のナビゲーションで **[請求]、[サービスを購入する]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-179">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="7e330-180">**[サービスを購入する]** ページで、**[Microsoft 365 E5]**、**[無料試用版を取得]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-180">On the **Purchase services** page, click **Microsoft 365 E5**, and then click **Get free trial**.</span></span>

4. <span data-ttu-id="7e330-181">**[Microsoft 365 E5 試用版]** ページで、テキスト メッセージを受信するか電話を受けるかを選択し、電話番号を入力して、**[テキスト メッセージを送信する]** または **[電話する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-181">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span> <span data-ttu-id="7e330-182">検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e330-182">Perform the verification.</span></span>

5. <span data-ttu-id="7e330-183">**[注文の確認]** ページで、 **[今すぐ実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-183">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="7e330-184">**[注文の受領書]** ページで、**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-184">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="7e330-185">Microsoft 365 管理センターで、**[ユーザー]、[アクティブなユーザー]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-185">In the Microsoft 365 admin center, click **Users > Active users**.</span></span>

8. <span data-ttu-id="7e330-186">**アクティブ ユーザー** で、自分の管理者アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-186">In **Active users**, click your administrator account.</span></span>

9. <span data-ttu-id="7e330-187">**[ライセンスとアプリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-187">Click **Licenses and apps**.</span></span>

10. <span data-ttu-id="7e330-188">Office 365 Enterprise E5 のライセンスを無効にして、Microsoft 365 E5 のライセンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7e330-188">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="7e330-189">**[変更を保存]** をクリックして、ユーザー アカウント情報ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7e330-189">Click **Save changes** and then close the user account information pane.</span></span>

<span data-ttu-id="7e330-190">次に、その他のすべてのアカウント (User 2、User 3、User 4、および User 5) に前述の手順 8 から 11 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7e330-190">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e330-191">Microsoft 365 E5 の試用版サブスクリプションは 30 日間有効です。</span><span class="sxs-lookup"><span data-stu-id="7e330-191">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="7e330-192">永続的なテスト環境の場合は、少数のライセンスを使用して、この試用版のサブスクリプションを有料サブスクリプションに変換します。</span><span class="sxs-lookup"><span data-stu-id="7e330-192">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="7e330-193">テスト環境は、次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="7e330-193">Your test environment now has:</span></span>
  
- <span data-ttu-id="7e330-194">Microsoft 365 E5 の試用版サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="7e330-194">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="7e330-195">すべての適切なユーザー アカウント (全体管理者のみまたは 5 つすべてのユーザー アカウントのどちらか) が、Microsoft 365 E5 を使用できるようになっている。</span><span class="sxs-lookup"><span data-stu-id="7e330-195">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="7e330-196">Office 365 と Enterprise Security + Management (EMS) の両方を含む Microsoft 365 E5 を追加した最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="7e330-196">Here is your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Microsoft 365 Enterprise テスト環境のフェーズ 3](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="7e330-198">フェーズ 4: Windows 10 Enterprise コンピューターを作成する</span><span class="sxs-lookup"><span data-stu-id="7e330-198">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="7e330-199">このフェーズでは、物理コンピューター、仮想マシン、Azure 仮想マシンのいずれかとして Windows 10 Enterprise を実行するスタンドアロン コンピューターを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e330-199">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="7e330-200">物理コンピューター</span><span class="sxs-lookup"><span data-stu-id="7e330-200">Physical computer</span></span>

<span data-ttu-id="7e330-p109">パーソナル コンピューターを入手し、Windows 10 Enterprise をインストールします。Windows 10 Enterprise 試用版は、[ここ](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7e330-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="7e330-203">仮想マシン</span><span class="sxs-lookup"><span data-stu-id="7e330-203">Virtual machine</span></span>

<span data-ttu-id="7e330-p110">任意のハイパーバイザーを使用して仮想マシンを作成し、そのマシンに Windows 10 Enterprise をインストールします。Windows 10 Enterprise 試用版は、[ここ](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7e330-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="7e330-206">Azure での仮想マシン</span><span class="sxs-lookup"><span data-stu-id="7e330-206">Virtual machine in Azure</span></span>

<span data-ttu-id="7e330-p111">Microsoft Azure で Windows 10 の仮想マシンを作成するには、***Visual Studio ベースのサブスクリプションが必要***です。このサブスクリプションにより、Windows 10 Enterprise のイメージにアクセスできます。試用版や有料のサブスクリプションなど、その他の種類の Azure サブスクリプションでは、このイメージにアクセスできません。最新情報については、「[Azure で Windows クライアントを開発/テスト シナリオに使用する](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e330-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e330-p112">次のコマンド セットは、最新バージョンの Azure PowerShell を使用します。「[Azure PowerShell の概要](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)」を参照してください。このコマンド セットにより、WIN10 という名前の Windows 10 Enterprise の仮想マシンと、このマシンに必要なすべてのインフラストラクチャをビルドします。これには、リソース グループ、ストレージ アカウント、仮想ネットワークが含まれます。Azure インフラストラクチャ サービスを既に使い慣れている場合は、これらの手順は展開済みのインフラストラクチャに合わせて、実行してください。</span><span class="sxs-lookup"><span data-stu-id="7e330-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="7e330-214">最初に、Microsoft PowerShell プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="7e330-214">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="7e330-215">次のコマンドを使用して Azure アカウントにログインします。</span><span class="sxs-lookup"><span data-stu-id="7e330-215">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="7e330-216">次のコマンドを使用して、サブスクリプションの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="7e330-216">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="7e330-p113">Azure サブスクリプションを設定します。二重引用符内のすべて (「\<」と「>」の文字を含む) を正しい名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7e330-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="7e330-p114">次に、新しいリソース グループを作成します。一意のリソース グループ名を決定するには、このコマンドを使用して既存のリソース グループを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7e330-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="7e330-p115">これらのコマンドを使用して、新しいリソース グループを作成します。二重引用符内のすべて (「\<」と「>」の文字を含む) を正しい名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7e330-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="7e330-p116">次に、これらのコマンドを使用して新しい仮想ネットワークと WIN10 仮想マシンを作成します。ダイアログ ボックスが表示されたら、WIN10 の名前とローカル管理者アカウントのパスワードを指定し、これらを安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="7e330-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="7e330-225">フェーズ 5: Windows 10 のコンピューターを Azure AD に参加させる</span><span class="sxs-lookup"><span data-stu-id="7e330-225">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="7e330-226">Windows 10 Enterprise の物理マシンまたは仮想マシンの作成後、ローカル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="7e330-226">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e330-227">Azure の仮想マシンの場合は、[この手順](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)に従います。</span><span class="sxs-lookup"><span data-stu-id="7e330-227">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="7e330-228">次に、WIN10 コンピューターを Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加させます。</span><span class="sxs-lookup"><span data-stu-id="7e330-228">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="7e330-229">WIN10 コンピューターのデスクトップで、**[スタート] > [設定] > [アカウント] > [職場または学校にアクセスする] > [接続]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-229">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="7e330-230">**[職場または学校アカウントの設定]** ダイアログ ボックスで、**[このデバイスを Azure Active Directory に参加させる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-230">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="7e330-231">**[職場または学校アカウント]** に Microsoft 365 E5 サブスクリプションの全体管理者のアカウント名を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-231">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="7e330-232">**[パスワードの入力]** に全体管理者アカウントのパスワードを入力して、**[サインイン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-232">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="7e330-233">この組織で合っているか確認するダイアログ ボックスが表示されたら、**[参加]** をクリックしてから **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-233">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="7e330-234">[設定] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7e330-234">Close the settings window.</span></span>
    
<span data-ttu-id="7e330-235">次に、WIN10 コンピューターに Office 365 ProPlus をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7e330-235">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="7e330-236">Microsoft Edge ブラウザーを開いて、グローバル管理者アカウントの認証資格情報を使用して、Office ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="7e330-236">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="7e330-237">詳細については、「[一般法人向け Office 365 にサインインする場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e330-237">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="7e330-238">**[Microsoft Office Home]** タブで、**[Office のインストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-238">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="7e330-239">操作内容を確認するダイアログ ボックスが表示されたら、**[実行]** をクリックし、**[ユーザー アカウント制御]** の **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-239">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="7e330-p118">Office のインストールが完了するまで待ちます。**[準備が完了しました]** が表示されたら、**[閉じる]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="7e330-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="7e330-242">最終的な環境をここに示します。</span><span class="sxs-lookup"><span data-stu-id="7e330-242">Here is your resulting environment.</span></span>

![Microsoft 365 Enterprise テスト環境のフェーズ 5](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="7e330-244">これには、以下を備えた WIN10 コンピューターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e330-244">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="7e330-245">Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加している。</span><span class="sxs-lookup"><span data-stu-id="7e330-245">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="7e330-246">Microsoft Intune (EMS) で Azure AD デバイスとして登録されている。</span><span class="sxs-lookup"><span data-stu-id="7e330-246">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="7e330-247">Office 365 ProPlus がインストールされている。</span><span class="sxs-lookup"><span data-stu-id="7e330-247">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="7e330-248">これで、[Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) の追加機能を試せるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7e330-248">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="7e330-249">次の手順</span><span class="sxs-lookup"><span data-stu-id="7e330-249">Next steps</span></span>

<span data-ttu-id="7e330-250">こうした追加のテスト ラボ ガイドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7e330-250">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="7e330-251">ID</span><span class="sxs-lookup"><span data-stu-id="7e330-251">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="7e330-252">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="7e330-252">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="7e330-253">情報保護</span><span class="sxs-lookup"><span data-stu-id="7e330-253">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="7e330-254">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e330-254">See also</span></span>

[<span data-ttu-id="7e330-255">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="7e330-255">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7e330-256">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="7e330-256">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7e330-257">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="7e330-257">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
