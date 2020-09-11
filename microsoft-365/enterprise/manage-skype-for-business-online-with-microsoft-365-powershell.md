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
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430036"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="ad591-103">PowerShell を使用して Skype for Business Online を管理する</span><span class="sxs-lookup"><span data-stu-id="ad591-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="ad591-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="ad591-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ad591-105">Skype for Business Online 管理者は、ポリシーの管理を担当します。</span><span class="sxs-lookup"><span data-stu-id="ad591-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="ad591-106">これらのタスクの一部は Microsoft 365 管理センターで実行できますが、PowerShell で実行しやすいものもあります。</span><span class="sxs-lookup"><span data-stu-id="ad591-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="ad591-107">始める前に</span><span class="sxs-lookup"><span data-stu-id="ad591-107">Before you start</span></span>

<span data-ttu-id="ad591-108">[Skype for Business Online Windows PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366)をダウンロードしてインストールし、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ad591-108">Download and install the [Skype for Business Online Windows PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-skype-for-business-online-admin-credentials"></a><span data-ttu-id="ad591-109">Skype for Business Online の管理者資格情報を使用して接続する</span><span class="sxs-lookup"><span data-stu-id="ad591-109">Connect using Skype for Business Online admin credentials</span></span>

1. <span data-ttu-id="ad591-110">Windows PowerShell コマンド プロンプト ウィンドを開いて次のコマンドを実行します:</span><span class="sxs-lookup"><span data-stu-id="ad591-110">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="ad591-111">[**Windows PowerShell 資格情報の要求**] ダイアログ ボックスに Skype for Business Online 管理者のアカウント名とパスワードを入力し、[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad591-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="ad591-112">多要素認証の管理者アカウントを使用して接続する</span><span class="sxs-lookup"><span data-stu-id="ad591-112">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="ad591-113">Windows PowerShell コマンド プロンプト ウィンドを開いて次のコマンドを実行します:</span><span class="sxs-lookup"><span data-stu-id="ad591-113">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="ad591-114">**New-CsOnlineSession** コマンドでダイアログ ボックスが表示されたら、Skype for Business Online 管理者のアカウント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad591-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="ad591-115">[**アカウントにサインイン**] ダイアログ ボックスで、Skype for Business Online 管理者のパスワードを入力し、[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad591-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="ad591-116">[**アカウントにサインイン**] ダイアログ ボックスで手順に従い、確認コードなどのその他の認証情報を追加し、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad591-116">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="ad591-117">詳しくは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad591-117">For more information, see:</span></span>
  
- [<span data-ttu-id="ad591-118">PowerShell を使用して Skype for Business Online を管理する</span><span class="sxs-lookup"><span data-stu-id="ad591-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="ad591-119">PowerShell を使用してユーザーごとに Skype for Business Online のポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ad591-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="ad591-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad591-120">See also</span></span>

[<span data-ttu-id="ad591-121">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="ad591-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ad591-122">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="ad591-122">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="ad591-123">Skype for Business PowerShell のコマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="ad591-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
