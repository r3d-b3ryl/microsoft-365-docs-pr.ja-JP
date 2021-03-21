---
title: PowerShell を使用して Skype for Business Online を管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: PowerShell for Microsoft 365 を使用して、Skype for Business Online ポリシー、ユーザー単位ポリシー、会議の設定を管理します。
ms.openlocfilehash: 4477dadf0ea38a81ac0ae282da3f74fc12f3406f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916682"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="db3f7-103">PowerShell を使用して Skype for Business Online を管理する</span><span class="sxs-lookup"><span data-stu-id="db3f7-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="db3f7-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="db3f7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="db3f7-105">Skype for Business Online 管理者は、ポリシーの管理を担当します。</span><span class="sxs-lookup"><span data-stu-id="db3f7-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="db3f7-106">これらのタスクの一部は Microsoft 365 管理センターで実行できますが、PowerShell で実行しやすいものもあります。</span><span class="sxs-lookup"><span data-stu-id="db3f7-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="db3f7-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="db3f7-107">Before you start</span></span>

  > [!Note]
   > <span data-ttu-id="db3f7-108">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="db3f7-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="db3f7-109">最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="db3f7-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
<span data-ttu-id="db3f7-110">[Teams PowerShell モジュール](/microsoftteams/teams-powershell-install)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="db3f7-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>


## <a name="connect-using-admin-credentials"></a><span data-ttu-id="db3f7-111">管理者の資格情報を使用して接続する</span><span class="sxs-lookup"><span data-stu-id="db3f7-111">Connect using admin credentials</span></span>

1. <span data-ttu-id="db3f7-112">Windows PowerShell コマンド プロンプト ウィンドを開き、次のコマンドを実行します:</span><span class="sxs-lookup"><span data-stu-id="db3f7-112">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. <span data-ttu-id="db3f7-113">[**Windows PowerShell 資格情報の要求**] ダイアログ ボックスに管理者のアカウント名とパスワードを入力し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db3f7-113">In the **Windows PowerShell Credential Request** dialog box, type your administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="db3f7-114">多要素認証の管理者アカウントを使用して接続する</span><span class="sxs-lookup"><span data-stu-id="db3f7-114">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="db3f7-115">Windows PowerShell コマンド プロンプト ウィンドを開いて次のコマンドを実行します:</span><span class="sxs-lookup"><span data-stu-id="db3f7-115">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. <span data-ttu-id="db3f7-116">ダイアログ ボックスが表示されたら、Skype for Business Online 管理者のアカウント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="db3f7-116">When prompted enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="db3f7-117">[**アカウントにサインイン**] ダイアログ ボックスで、Skype for Business Online 管理者のパスワードを入力し、[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db3f7-117">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="db3f7-118">[**アカウントにサインイン**] ダイアログ ボックスで手順に従い、確認コードなどのその他の認証情報を追加し、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db3f7-118">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="db3f7-119">詳しくは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db3f7-119">For more information, see:</span></span>
  
- [<span data-ttu-id="db3f7-120">PowerShell を使用して Skype for Business Online を管理する</span><span class="sxs-lookup"><span data-stu-id="db3f7-120">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="db3f7-121">PowerShell を使用してユーザーごとに Skype for Business Online のポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="db3f7-121">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="db3f7-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="db3f7-122">See also</span></span>

[<span data-ttu-id="db3f7-123">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="db3f7-123">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="db3f7-124">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="db3f7-124">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="db3f7-125">Skype for Business PowerShell のコマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="db3f7-125">Skype for Business PowerShell cmdlet references</span></span>](/powershell/module/skype/?view=skype-ps)