---
title: PowerShell を使用してパスワードを管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: PowerShell を使用してパスワードを管理する方法について説明します。
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073214"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="7e72b-103">PowerShell を使用してパスワードを管理する</span><span class="sxs-lookup"><span data-stu-id="7e72b-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="7e72b-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="7e72b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7e72b-105">Microsoft 365 の PowerShell を microsoft 365 管理センターの代わりとして使用して、Microsoft 365 でパスワードを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7e72b-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="7e72b-106">この記事のコマンドブロックで変数の値を指定する必要がある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e72b-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="7e72b-107">コマンドブロックをクリップボードにコピーして、メモ帳または PowerShell 統合スクリプト環境 (ISE) に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7e72b-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="7e72b-108">変数の値を入力し、"<" と ">" の文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="7e72b-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="7e72b-109">PowerShell ウィンドウまたは PowerShell ISE でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e72b-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="7e72b-110">Graph 用 Azure Active Directory PowerShell モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="7e72b-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="7e72b-111">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="7e72b-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="7e72b-112">パスワードを設定する</span><span class="sxs-lookup"><span data-stu-id="7e72b-112">Set a password</span></span>

<span data-ttu-id="7e72b-113">ユーザーアカウントのパスワードを指定するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e72b-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="7e72b-114">ユーザーにパスワードの変更を強制する</span><span class="sxs-lookup"><span data-stu-id="7e72b-114">Force a user to change their password</span></span>

<span data-ttu-id="7e72b-115">次のコマンドを使用してパスワードを設定し、ユーザーに新しいパスワードの変更を強制します。</span><span class="sxs-lookup"><span data-stu-id="7e72b-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="7e72b-116">次のコマンドを使用して、パスワードを設定し、ユーザーが次回サインインしたときに新しいパスワードを強制的に変更するようにします。</span><span class="sxs-lookup"><span data-stu-id="7e72b-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="7e72b-117">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="7e72b-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="7e72b-118">最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="7e72b-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="7e72b-119">パスワードを設定する</span><span class="sxs-lookup"><span data-stu-id="7e72b-119">Set a password</span></span>

<span data-ttu-id="7e72b-120">ユーザーアカウントのパスワードを指定するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e72b-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="7e72b-121">ユーザーにパスワードの変更を強制する</span><span class="sxs-lookup"><span data-stu-id="7e72b-121">Force a user to change their password</span></span>

<span data-ttu-id="7e72b-122">ユーザーが自分のパスワードを変更するように強制するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e72b-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="7e72b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e72b-123">See also</span></span>

[<span data-ttu-id="7e72b-124">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="7e72b-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7e72b-125">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="7e72b-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7e72b-126">Microsoft 365 用 PowerShell の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="7e72b-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

