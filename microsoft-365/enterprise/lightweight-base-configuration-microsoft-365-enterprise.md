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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: このテスト ラボ ガイドを使用して、Microsoft 365 for enterprise をテストする軽量なテスト環境を作成します。
ms.openlocfilehash: 2de0760cef7339f62229575b1e0a54b3c67a4e9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909708"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="35efa-103">軽量な基本構成</span><span class="sxs-lookup"><span data-stu-id="35efa-103">The lightweight base configuration</span></span>

<span data-ttu-id="35efa-104">*このテスト ラボ ガイドは、Microsoft 365 for enterprise と 365 Enterprise テストOffice両方に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="35efa-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="35efa-105">この記事では、Microsoft 365 E5 サブスクリプションと Windows 10 Enterprise を実行しているコンピューターを使用して簡略化された環境を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="35efa-105">This article describes how to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span>

![軽量な Microsoft 365 Enterprise テスト環境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="35efa-107">軽量なテスト環境を作成するには、次の 5 つのフェーズが必要です。</span><span class="sxs-lookup"><span data-stu-id="35efa-107">Creating a lightweight test environment involves five phases:</span></span>
- [<span data-ttu-id="35efa-108">フェーズ 1: Microsoft 365 E5 サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="35efa-108">Phase 1: Create your Microsoft 365 E5 subscription</span></span>](#phase-1-create-your-microsoft-365-e5-subscription)
- [<span data-ttu-id="35efa-109">フェーズ 2: Office 365 試用版サブスクリプションを構成する</span><span class="sxs-lookup"><span data-stu-id="35efa-109">Phase 2: Configure your Office 365 trial subscription</span></span>](#phase-2-configure-your-office-365-trial-subscription)
- [<span data-ttu-id="35efa-110">フェーズ 3: Microsoft 365 E5 の試用版サブスクリプションを追加する</span><span class="sxs-lookup"><span data-stu-id="35efa-110">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [<span data-ttu-id="35efa-111">フェーズ 4: Windows 10 Enterprise コンピューターを作成する</span><span class="sxs-lookup"><span data-stu-id="35efa-111">Phase 4: Create a Windows 10 Enterprise computer</span></span>](#phase-4-create-a-windows-10-enterprise-computer)
- [<span data-ttu-id="35efa-112">フェーズ 5: Windows 10 のコンピューターを Azure AD に参加させる</span><span class="sxs-lookup"><span data-stu-id="35efa-112">Phase 5: Join your Windows 10 computer to Azure AD</span></span>](#phase-5-join-your-windows-10-computer-to-azure-ad)

<span data-ttu-id="35efa-113">結果の環境を使用して [、Microsoft 365 for](https://www.microsoft.com/microsoft-365/enterprise)enterprise の機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="35efa-113">Use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="35efa-115">Microsoft 365 for enterprise Test Lab Guide スタックのすべての記事への視覚的なマップについては [、「Microsoft 365 for enterprise Test Lab Guide Stack」を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="35efa-115">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, see [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

>[!NOTE]
><span data-ttu-id="35efa-116">この記事を印刷しておき、30 日間の Office 365 試用版サブスクリプションの終了後にこの環境で必要になる特定の情報を記録しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35efa-116">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="35efa-117">試用版サブスクリプションは、追加で 30 日間まで簡単に延長できます。</span><span class="sxs-lookup"><span data-stu-id="35efa-117">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="35efa-118">永続的なテスト環境の場合は、別個の Azure AD テナントと少数のライセンスを使用して、新しい有料サブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="35efa-118">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="35efa-119">フェーズ 1: Microsoft 365 E5 サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="35efa-119">Phase 1: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="35efa-120">Microsoft 365 E5 試用版サブスクリプションから始め、Microsoft 365 E5 サブスクリプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="35efa-120">We start with an Microsoft 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

>[!NOTE]
><span data-ttu-id="35efa-121">テスト環境が現在持っている有料サブスクリプションとは別の Azure AD テナントを持つOffice 365 の試用版サブスクリプションを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35efa-121">We recommend that you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="35efa-122">この分離により、テスト テナント内のユーザーとグループを追加および削除して、実稼働サブスクリプションに影響を与えることなく行えるという意味です。</span><span class="sxs-lookup"><span data-stu-id="35efa-122">This separation means that you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>

<span data-ttu-id="35efa-123">Microsoft 365 E5 試用版サブスクリプションを開始するには、最初に、架空の会社名と新しい Microsoft アカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="35efa-123">To start your Microsoft 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="35efa-p103">この会社名には、会社名 Contoso のバリエーションを使用するようお勧めします (必須ではありません)。Contoso は、Microsoft のサンプル コンテンツで使用される架空の会社名です。ここに架空の会社名を記録してください:</span><span class="sxs-lookup"><span data-stu-id="35efa-p103">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![線](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="35efa-p104">新しい Microsoft アカウントにサインアップするには、[https://outlook.com](https://outlook.com) に移動して、新しい電子メール アカウントとアドレスでアカウントを作成します。このアカウントを使用して、Office 365 にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="35efa-p104">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
    - <span data-ttu-id="35efa-129">ここに新しいアカウントの姓名を記録してください:</span><span class="sxs-lookup"><span data-stu-id="35efa-129">Record the first and last name of your new account here:</span></span> ![線](../media/Common-Images/TableLine.png)
    
    - <span data-ttu-id="35efa-131">新しいメール アカウント アドレスをここに記録します。</span><span class="sxs-lookup"><span data-stu-id="35efa-131">Record the new email account address here:</span></span> ![線](../media/Common-Images/TableLine.png)<span data-ttu-id="35efa-133">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="35efa-133">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="35efa-134">Office 365 E5 試用版サブスクリプションにサインアップする</span><span class="sxs-lookup"><span data-stu-id="35efa-134">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="35efa-135">ブラウザーで、 に移動します [https://aka.ms/e5trial](https://aka.ms/e5trial) 。</span><span class="sxs-lookup"><span data-stu-id="35efa-135">In your browser, go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="35efa-136">**[365 E5 365 E5]** ページOfficeの手順 1 で、新しいメール アカウント のアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="35efa-136">In step 1 of the **Thank you for choosing Office 365 E5** page, enter your new email account address.</span></span>
3. <span data-ttu-id="35efa-137">証跡サブスクリプション プロセスの手順 2 で、要求された情報を入力し、検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="35efa-137">In step 2 of the trail subscription process, enter the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="35efa-138">手順 3 で、組織名を入力し、サブスクリプションのグローバル管理者になるアカウント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="35efa-138">In step 3, enter an organization name and then an account name that will be the global admin for the subscription.</span></span>
5. <span data-ttu-id="35efa-139">手順 4 では、ここにサインイン ページを記録します (選択してコピー):</span><span class="sxs-lookup"><span data-stu-id="35efa-139">For step 4, record the sign-in page here (select and copy):</span></span> ![線](../media/Common-Images/TableLine.png)
6. <span data-ttu-id="35efa-141">ここにユーザー ID を記録します: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="35efa-141">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="35efa-142">安全な場所に入力したパスワードを記録します。</span><span class="sxs-lookup"><span data-stu-id="35efa-142">Record the password that you entered in a secure location.</span></span>
   <span data-ttu-id="35efa-143">この値を **全体管理者名** と呼ぶことにします。</span><span class="sxs-lookup"><span data-stu-id="35efa-143">This value will be referred to as the **global administrator name**.</span></span>
7. <span data-ttu-id="35efa-144">[セットアップ **に移動] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-144">Select **Go to Setup**.</span></span>
8. <span data-ttu-id="35efa-145">[Office 365 E5 セットアップ] で、[組織 **の .onmicrosoft.com** を使用してメールとサインインを続行する] を選択し、[終了して後で続行する] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-145">In Office 365 E5 Setup, select **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then select **Exit and continue later**.</span></span>

<span data-ttu-id="35efa-146">Microsoft 365 管理センターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35efa-146">You should see the Microsoft 365 admin center.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="35efa-147">フェーズ 2: Office 365 試用版サブスクリプションを構成する</span><span class="sxs-lookup"><span data-stu-id="35efa-147">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="35efa-148">このフェーズでは、サブスクリプションを構成してユーザーを追加し、Office 365 E5 ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="35efa-148">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="35efa-149">コンピューターから Azure Active Directory PowerShell for Graph モジュールを使用してサブスクリプションに接続するには、「PowerShell を使用して [Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)に接続する」の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="35efa-149">To connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer, use the instructions in [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
    
<span data-ttu-id="35efa-150">[資格情報 **Windows PowerShell] ダイアログ** ボックスで、グローバル管理者名 (たとえば、jdoe@contosotoycompany.onmicrosoft.com) *と* パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="35efa-150">In the **Windows PowerShell Credential Request** dialog box, enter the global administrator name (for example, *jdoe@contosotoycompany.onmicrosoft.com*) and password.</span></span>
  
<span data-ttu-id="35efa-151">組織名 *(contosotoycompany* など)、場所の 2 文字の国コード、共通のアカウント パスワードを入力し、PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="35efa-151">Fill in your organization name (for example, *contosotoycompany*), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="35efa-152">ここで共通のパスワードを使用するのは、自動化およびテスト環境の構成を容易にするためです。</span><span class="sxs-lookup"><span data-stu-id="35efa-152">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="35efa-153">運用環境のサブスクリプションは避けるように強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35efa-153">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="35efa-154">将来の参照のために重要な情報を記録する</span><span class="sxs-lookup"><span data-stu-id="35efa-154">Record key information for future reference</span></span>

<span data-ttu-id="35efa-155">これらの値をまだ記録していない場合は、次の値を記録します。</span><span class="sxs-lookup"><span data-stu-id="35efa-155">If you haven't already recorded these values, record them now:</span></span>
  
- <span data-ttu-id="35efa-156">グローバル管理者名:</span><span class="sxs-lookup"><span data-stu-id="35efa-156">Global administrator name:</span></span> ![線](../media/Common-Images/TableLine.png)<span data-ttu-id="35efa-158">.onmicrosoft.com (フェーズ 1 のステップ 6 から)</span><span class="sxs-lookup"><span data-stu-id="35efa-158">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="35efa-159">このアカウントのパスワードも安全な場所に記録してください。</span><span class="sxs-lookup"><span data-stu-id="35efa-159">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="35efa-160">試用版サブスクリプションの組織名:</span><span class="sxs-lookup"><span data-stu-id="35efa-160">Your trial subscription organization name:</span></span> ![線](../media/Common-Images/TableLine.png) <span data-ttu-id="35efa-162">(フェーズ 1 のステップ 4 から)</span><span class="sxs-lookup"><span data-stu-id="35efa-162">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="35efa-163">User 2、User 3、User 4、および User 5 のアカウントを一覧表示するには、次に示すコマンドを Windows PowerShell 用 Microsoft Azure Active Directory モジュールのプロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="35efa-163">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="35efa-164">ここにアカウント名を記録してください:</span><span class="sxs-lookup"><span data-stu-id="35efa-164">Record the account names here:</span></span>
    
  - <span data-ttu-id="35efa-165">ユーザー 2 アカウント名: user2@</span><span class="sxs-lookup"><span data-stu-id="35efa-165">User 2 account name: user2@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="35efa-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="35efa-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="35efa-168">ユーザー 3 アカウント名: user3@</span><span class="sxs-lookup"><span data-stu-id="35efa-168">User 3 account name: user3@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="35efa-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="35efa-170">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="35efa-171">ユーザー 4 アカウント名: user4@</span><span class="sxs-lookup"><span data-stu-id="35efa-171">User 4 account name: user4@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="35efa-173">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="35efa-173">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="35efa-174">ユーザー 5 アカウント名: user5@</span><span class="sxs-lookup"><span data-stu-id="35efa-174">User 5 account name: user5@</span></span>![線](../media/Common-Images/TableLine.png)<span data-ttu-id="35efa-176">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="35efa-176">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="35efa-177">これらのアカウントの共通パスワードも安全な場所に記録してください。</span><span class="sxs-lookup"><span data-stu-id="35efa-177">Also record the common password for these accounts in a secure location.</span></span>
   
### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="35efa-178">Office 365 テスト環境を使用する</span><span class="sxs-lookup"><span data-stu-id="35efa-178">Using an Office 365 test environment</span></span>

<span data-ttu-id="35efa-179">365 テスト環境Office必要な場合は、この記事の残りの部分を読む必要があります。</span><span class="sxs-lookup"><span data-stu-id="35efa-179">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="35efa-180">Office 365 と Microsoft 365 の両方に適用される追加のテスト ラボ ガイドについては [、「Microsoft 365 for enterprise Test Lab Guides」を参照してください](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="35efa-180">For additional Test Lab Guides that apply to both Office 365 and Microsoft 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="35efa-181">フェーズ 3: Microsoft 365 E5 の試用版サブスクリプションを追加する</span><span class="sxs-lookup"><span data-stu-id="35efa-181">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="35efa-182">このフェーズでは、Microsoft 365 E5 試用版サブスクリプションにサインアップして、Office 365 E5 試用版サブスクリプションと同じ組織に追加します。</span><span class="sxs-lookup"><span data-stu-id="35efa-182">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="35efa-183">まず、Microsoft 365 E5 試用版サブスクリプションを追加して、新しい Microsoft 365 ライセンスを全体管理者アカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="35efa-183">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="35efa-184">インターネット ブラウザーのプライベート ウィンドウで、グローバル管理者アカウントの資格情報を使用して、 で Microsoft 365 管理センターにサインインします [https://admin.microsoft.com](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="35efa-184">In an internet browser private window, use your global administrator account credentials to sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="35efa-185">**[Microsoft 365 管理** センター] ページの左側のナビゲーションで、[課金と購入サービス>**選択します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-185">On the **Microsoft 365 admin center** page, in the left navigation, select **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="35efa-186">[サービスの **購入] ページで\*\*\*\*、[Microsoft 365 E5]** を選択し、[無料試用版の取得 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-186">On the **Purchase services** page, select **Microsoft 365 E5**, and then select **Get free trial**.</span></span>

4. <span data-ttu-id="35efa-187">**[Microsoft 365 E5 試用版**] ページで、テキスト メッセージまたは電話を受け取り、電話番号を入力し、[テキスト] または [電話] を選択 **します。**</span><span class="sxs-lookup"><span data-stu-id="35efa-187">On the **Microsoft 365 E5 Trial** page, decide to receive a text message or a phone call, enter your phone number, and then select **Text me** or **Call me**.</span></span> <span data-ttu-id="35efa-188">検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="35efa-188">Perform the verification.</span></span>

5. <span data-ttu-id="35efa-189">[注文の **確認] ページで** 、[今すぐ試す] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-189">On the **Confirm your order** page, select **Try now**.</span></span>

6. <span data-ttu-id="35efa-190">[注文受領 **書] ページで** 、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-190">On the **Order receipt** page, select **Continue**.</span></span>

7. <span data-ttu-id="35efa-191">Microsoft 365 管理センターで、[アクティブ ユーザー] を **選択>選択します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-191">In the Microsoft 365 admin center, select **Users > Active users**.</span></span>

8. <span data-ttu-id="35efa-192">[ **アクティブ なユーザー]** で、管理者アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="35efa-192">In **Active users**, select your administrator account.</span></span>

9. <span data-ttu-id="35efa-193">[ライセンス **とアプリ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-193">Select **Licenses and apps**.</span></span>

10. <span data-ttu-id="35efa-194">Office 365 Enterprise E5 のライセンスを無効にして、Microsoft 365 E5 のライセンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="35efa-194">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="35efa-195">[変更 **の保存]** を選択し、ユーザー アカウント情報ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="35efa-195">Select **Save changes**, and then close the user account information pane.</span></span>

<span data-ttu-id="35efa-196">次に、その他のすべてのアカウント (User 2、User 3、User 4、および User 5) に前述の手順 8 から 11 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="35efa-196">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="35efa-197">Microsoft 365 E5 試用版サブスクリプションの長さは 30 日間です。</span><span class="sxs-lookup"><span data-stu-id="35efa-197">The length of the Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="35efa-198">永続的なテスト環境の場合は、少数のライセンスを使用して、この試用版のサブスクリプションを有料サブスクリプションに変換します。</span><span class="sxs-lookup"><span data-stu-id="35efa-198">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span>
  
<span data-ttu-id="35efa-199">テスト環境は、次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="35efa-199">Your test environment now has:</span></span>
  
- <span data-ttu-id="35efa-200">Microsoft 365 E5 の試用版サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="35efa-200">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="35efa-201">すべての適切なユーザー アカウント (全体管理者のみまたは 5 つすべてのユーザー アカウントのどちらか) が、Microsoft 365 E5 を使用できるようになっている。</span><span class="sxs-lookup"><span data-stu-id="35efa-201">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="35efa-202">Microsoft 365 E5 を追加する結果の構成は、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="35efa-202">Your resulting configuration, which adds Microsoft 365 E5, looks like this:</span></span>
  
![Microsoft 365 Enterprise テスト環境のフェーズ 3](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="35efa-204">フェーズ 4: Windows 10 Enterprise コンピューターを作成する</span><span class="sxs-lookup"><span data-stu-id="35efa-204">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="35efa-205">このフェーズでは、物理コンピューター、仮想マシン、Azure 仮想マシンのいずれかとして Windows 10 Enterprise を実行するスタンドアロン コンピューターを作成します。</span><span class="sxs-lookup"><span data-stu-id="35efa-205">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="35efa-206">物理コンピューター</span><span class="sxs-lookup"><span data-stu-id="35efa-206">Physical computer</span></span>

<span data-ttu-id="35efa-207">個人用コンピューターで、Windows 10 Enterprise をインストールします。</span><span class="sxs-lookup"><span data-stu-id="35efa-207">On a personal computer, install Windows 10 Enterprise.</span></span> <span data-ttu-id="35efa-208">Windows 10 Enterprise 試用版は、こちらからダウンロード [できます](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="35efa-208">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="35efa-209">仮想マシン</span><span class="sxs-lookup"><span data-stu-id="35efa-209">Virtual machine</span></span>

<span data-ttu-id="35efa-210">選択したハイパーバイザーを使用して仮想マシンを作成し、Windows 10 Enterprise をインストールします。</span><span class="sxs-lookup"><span data-stu-id="35efa-210">Use the hypervisor of your choice to create a virtual machine, and then install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="35efa-211">Windows 10 Enterprise 試用版は、こちらからダウンロード [できます](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="35efa-211">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="35efa-212">Azure での仮想マシン</span><span class="sxs-lookup"><span data-stu-id="35efa-212">Virtual machine in Azure</span></span>

<span data-ttu-id="35efa-p111">Microsoft Azure で Windows 10 の仮想マシンを作成するには、***Visual Studio ベースのサブスクリプションが必要*** です。このサブスクリプションにより、Windows 10 Enterprise のイメージにアクセスできます。試用版や有料のサブスクリプションなど、その他の種類の Azure サブスクリプションでは、このイメージにアクセスできません。最新情報については、「[Azure で Windows クライアントを開発/テスト シナリオに使用する](/azure/virtual-machines/windows/client-images)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35efa-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="35efa-216">次のコマンド セットは、Azure PowerShell の最新版を使用します。</span><span class="sxs-lookup"><span data-stu-id="35efa-216">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="35efa-217">「[Azure PowerShell の概要](/powershell/azureps-cmdlets-docs/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35efa-217">See [Get started with Azure PowerShell cmdlets](/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="35efa-218">これらのコマンドは、WIN10 という名前の Windows 10 Enterprise 仮想マシンと、リソース グループ、ストレージ アカウント、仮想ネットワークなど、必要なすべてのインフラストラクチャを構築します。</span><span class="sxs-lookup"><span data-stu-id="35efa-218">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="35efa-219">Azure インフラストラクチャ サービスについて既に理解している場合は、これらの手順を現在展開されているインフラストラクチャに合わせて調整します。</span><span class="sxs-lookup"><span data-stu-id="35efa-219">If you are already familiar with Azure infrastructure services, adapt these instructions to suit your currently deployed infrastructure.</span></span>
  
<span data-ttu-id="35efa-220">最初に、Microsoft PowerShell プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="35efa-220">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="35efa-221">このコマンドを使用して Azure アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="35efa-221">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="35efa-222">このコマンドを使用してサブスクリプション名を取得します。</span><span class="sxs-lookup"><span data-stu-id="35efa-222">Get your subscription name using this  command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="35efa-223">Azure サブスクリプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="35efa-223">Set your Azure subscription.</span></span> <span data-ttu-id="35efa-224">文字を含む引用符内のすべてを正しい \< and > 名前に置き換える。</span><span class="sxs-lookup"><span data-stu-id="35efa-224">Replace everything within the quotation marks, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="35efa-225">次に、新しいリソース グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="35efa-225">Next, create a new resource group.</span></span> <span data-ttu-id="35efa-226">一意のリソース グループ名を決定するには、このコマンドを使用して既存のリソース グループを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="35efa-226">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="35efa-227">これらのコマンドを使用して、新しいリソース グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="35efa-227">Create your new resource group with these commands.</span></span> <span data-ttu-id="35efa-228">文字を含む引用符内のすべてを正しい \< and > 名前に置き換える。</span><span class="sxs-lookup"><span data-stu-id="35efa-228">Replace everything within the quotation marks, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="35efa-229">次に、これらのコマンドを使用して、新しい仮想ネットワークと WIN10 仮想マシンを作成します。</span><span class="sxs-lookup"><span data-stu-id="35efa-229">Next, create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="35efa-230">ダイアログ ボックスが表示されたら、WIN10 の名前とローカル管理者アカウントのパスワードを指定し、これらを安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="35efa-230">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="35efa-231">フェーズ 5: Windows 10 のコンピューターを Azure AD に参加させる</span><span class="sxs-lookup"><span data-stu-id="35efa-231">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="35efa-232">Windows 10 Enterprise の物理マシンまたは仮想マシンの作成後、ローカル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="35efa-232">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35efa-233">Azure の仮想マシンの場合は、次の  [手順を使用して](/azure/virtual-machines/windows/connect-logon) 接続します。</span><span class="sxs-lookup"><span data-stu-id="35efa-233">For a virtual machine in Azure, use  [these instructions](/azure/virtual-machines/windows/connect-logon) to connect to it.</span></span>
  
<span data-ttu-id="35efa-234">次に、WIN10 コンピューターを Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加させます。</span><span class="sxs-lookup"><span data-stu-id="35efa-234">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="35efa-235">WIN10 コンピューターのデスクトップで、[スタート] > **[>** アカウント>アクセス] を>します。</span><span class="sxs-lookup"><span data-stu-id="35efa-235">On the desktop of the WIN10 computer, select **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="35efa-236">[仕事 **用アカウントまたは学校アカウントの設定]** ダイアログ ボックスで、[このデバイスを Azure Active Directory に **参加する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-236">In the **Set up a work or school account** dialog box, select **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="35efa-237">[ **仕事または学校のアカウント]** で、Microsoft 365 E5 サブスクリプションのグローバル管理者アカウント名を入力し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-237">In **Work or school account**, enter the global administrator account name of your Microsoft 365 E5 subscription, and then select **Next**.</span></span>
    
4. <span data-ttu-id="35efa-238">[ **パスワードの入力]** で、グローバル管理者アカウントのパスワードを入力し、[サインイン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-238">In **Enter password**, enter the password for your global administrator account, and then select **Sign in**.</span></span>
    
5. <span data-ttu-id="35efa-239">これが組織である必要がある場合は、[参加] を選択し、[完了] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-239">When prompted to make sure that this is your organization, select **Join**, and then select **Done**.</span></span>
    
6. <span data-ttu-id="35efa-240">[設定] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="35efa-240">Close the settings window.</span></span>
    
<span data-ttu-id="35efa-241">次に、WIN10 コンピューターに Microsoft 365 Apps for enterprise をインストールします。</span><span class="sxs-lookup"><span data-stu-id="35efa-241">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer:</span></span>
  
1. <span data-ttu-id="35efa-242">Microsoft Edge ブラウザーを開き、グローバル管理者アカウント資格情報を使用して [Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="35efa-242">Open the Microsoft Edge browser and sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="35efa-243">[ホーム]**タブMicrosoft Office、[** インストール]**を選択Office。**</span><span class="sxs-lookup"><span data-stu-id="35efa-243">On the **Microsoft Office Home** tab, select **Install Office**.</span></span>
    
3. <span data-ttu-id="35efa-244">操作を求めるメッセージが表示されたら、[**実行**] を選択し、[ユーザー アカウント制御]**で [は\*\*\*\*い] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="35efa-244">When prompted with what to do, select **Run**, and then select **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="35efa-245">Office のインストールが完了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="35efa-245">Wait for Office to complete its installation.</span></span> <span data-ttu-id="35efa-246">[すべて設定 **されている] が表示された場合は、[** 閉じる] **を 2 回** 選択します。</span><span class="sxs-lookup"><span data-stu-id="35efa-246">When you see **You're all set!**, select **Close** twice.</span></span>
    
<span data-ttu-id="35efa-247">結果の環境は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="35efa-247">Your resulting environment looks like this:</span></span>

![Microsoft 365 Enterprise テスト環境のフェーズ 5](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="35efa-249">これには、以下を備えた WIN10 コンピューターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="35efa-249">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="35efa-250">Microsoft 365 E5 サブスクリプションの Azure AD テナントに参加している。</span><span class="sxs-lookup"><span data-stu-id="35efa-250">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="35efa-251">Microsoft Intune (EMS) で Azure AD デバイスとして登録されている。</span><span class="sxs-lookup"><span data-stu-id="35efa-251">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="35efa-252">Microsoft 365 Apps for enterprise がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="35efa-252">Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="35efa-253">これで、エンタープライズ向け [Microsoft 365 の追加機能を試す準備ができました](https://www.microsoft.com/microsoft-365/enterprise)。</span><span class="sxs-lookup"><span data-stu-id="35efa-253">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="35efa-254">次の手順</span><span class="sxs-lookup"><span data-stu-id="35efa-254">Next steps</span></span>

<span data-ttu-id="35efa-255">こうした追加のテスト ラボ ガイドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="35efa-255">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="35efa-256">ID</span><span class="sxs-lookup"><span data-stu-id="35efa-256">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="35efa-257">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="35efa-257">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="35efa-258">情報保護</span><span class="sxs-lookup"><span data-stu-id="35efa-258">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="35efa-259">関連項目</span><span class="sxs-lookup"><span data-stu-id="35efa-259">See also</span></span>

[<span data-ttu-id="35efa-260">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="35efa-260">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="35efa-261">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="35efa-261">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="35efa-262">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="35efa-262">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)