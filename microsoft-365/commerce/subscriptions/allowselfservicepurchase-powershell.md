---
title: MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: AllowSelfServicePurchase PowerShell コマンドレットを使用してセルフサービス購入をオンまたはオフにする方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 03/18/2021
ms.openlocfilehash: 09161f69e72babe8270b339243d73444b93d9959
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333376"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="046e8-103">MSCommerce PowerShell モジュールに AllowSelfServicePurchase を使用する</span><span class="sxs-lookup"><span data-stu-id="046e8-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="046e8-104">**MSCommerce** PowerShell モジュールが [PowerShell ギャラリーで利用できます](https://aka.ms/allowselfservicepurchase-powershell-gallery)。</span><span class="sxs-lookup"><span data-stu-id="046e8-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="046e8-105">このモジュールには **、組織内のユーザー** がセルフサービス購入を行えるかどうかを制御できる **AllowSelfServicePurchase** の PolicyID パラメーター値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="046e8-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="046e8-106">**MSCommerce PowerShell** モジュールを使用すると、次の目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="046e8-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="046e8-107">**AllowSelfServicePurchase** パラメーター値の既定の状態を表示する (有効または無効のかどうか)</span><span class="sxs-lookup"><span data-stu-id="046e8-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="046e8-108">該当する製品の一覧とセルフサービス購入が有効か無効かを表示する</span><span class="sxs-lookup"><span data-stu-id="046e8-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="046e8-109">特定の製品の現在の設定を表示または変更して、有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="046e8-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="046e8-110">要件</span><span class="sxs-lookup"><span data-stu-id="046e8-110">Requirements</span></span>

<span data-ttu-id="046e8-111">**MSCommerce PowerShell モジュール** を使用するには、次が必要です。</span><span class="sxs-lookup"><span data-stu-id="046e8-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="046e8-112">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="046e8-112">A Windows 10 device</span></span>
- <span data-ttu-id="046e8-113">デバイスの管理者のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="046e8-113">Administrator permission for the device</span></span>
- <span data-ttu-id="046e8-114">テナントのグローバルまたは課金管理者の役割</span><span class="sxs-lookup"><span data-stu-id="046e8-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="046e8-115">MSCommerce PowerShell モジュールのインストール</span><span class="sxs-lookup"><span data-stu-id="046e8-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="046e8-116">WINDOWS 10 デバイスに **MSCommerce** PowerShell モジュールを 1 回インストールし、開始する各 PowerShell セッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="046e8-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="046e8-117">**PowerShell ギャラリーから MSCommerce** [PowerShell モジュールをダウンロードします](https://aka.ms/allowselfservicepurchase-powershell-gallery)。</span><span class="sxs-lookup"><span data-stu-id="046e8-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="046e8-118">**PowerShellGet を使用して MSCommerce** PowerShell モジュールをインストール **するには、** 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="046e8-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="046e8-119">MsCommerce を PowerShell セッションにインポートする</span><span class="sxs-lookup"><span data-stu-id="046e8-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="046e8-120">Windows 10 デバイスにモジュールをインストールした後、開始する各 PowerShell セッションにモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="046e8-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="046e8-121">PowerShell セッションにインポートするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="046e8-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="046e8-122">資格情報を使用して MSCommerce に接続する</span><span class="sxs-lookup"><span data-stu-id="046e8-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="046e8-123">資格情報を使用して PowerShell モジュールに接続するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="046e8-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="046e8-124">このコマンドは、現在の PowerShell セッションを Azure Active Directory テナントに接続します。</span><span class="sxs-lookup"><span data-stu-id="046e8-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="046e8-125">接続するテナントのユーザー名とパスワードを求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="046e8-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="046e8-126">資格情報に対して多要素認証が有効になっている場合は、対話型オプションを使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="046e8-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="046e8-127">AllowSelfServicePurchase の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="046e8-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="046e8-128">組織に基づいて **AllowSelfServicePurchase** パラメーター値と既定の状態の説明を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="046e8-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="046e8-129">セルフサービス購入製品とその状態の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="046e8-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="046e8-130">利用可能なすべてのセルフサービス購入製品の一覧とそれぞれの状態を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="046e8-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="046e8-131">次の表に、使用可能な製品とその **ProductId を示します**。</span><span class="sxs-lookup"><span data-stu-id="046e8-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="046e8-132">製品</span><span class="sxs-lookup"><span data-stu-id="046e8-132">Product</span></span> | <span data-ttu-id="046e8-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="046e8-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="046e8-134">ユーザーごとの Power Apps</span><span class="sxs-lookup"><span data-stu-id="046e8-134">Power Apps per user</span></span> | <span data-ttu-id="046e8-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="046e8-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="046e8-136">ユーザーごとの Power Automate</span><span class="sxs-lookup"><span data-stu-id="046e8-136">Power Automate per user</span></span> | <span data-ttu-id="046e8-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="046e8-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="046e8-138">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="046e8-138">Power Automate RPA</span></span> | <span data-ttu-id="046e8-139">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="046e8-139">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="046e8-140">Power BI Premium (スタンドアロン)</span><span class="sxs-lookup"><span data-stu-id="046e8-140">Power BI Premium (standalone)</span></span> | <span data-ttu-id="046e8-141">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="046e8-141">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="046e8-142">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="046e8-142">Power BI Pro</span></span> | <span data-ttu-id="046e8-143">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="046e8-143">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="046e8-144">Project Plan 1</span><span class="sxs-lookup"><span data-stu-id="046e8-144">Project Plan 1</span></span> | <span data-ttu-id="046e8-145">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="046e8-145">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="046e8-146">Project Plan 3</span><span class="sxs-lookup"><span data-stu-id="046e8-146">Project Plan 3</span></span> | <span data-ttu-id="046e8-147">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="046e8-147">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="046e8-148">Visio Plan 1</span><span class="sxs-lookup"><span data-stu-id="046e8-148">Visio Plan 1</span></span> | <span data-ttu-id="046e8-149">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="046e8-149">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="046e8-150">Visio Plan 2</span><span class="sxs-lookup"><span data-stu-id="046e8-150">Visio Plan 2</span></span> | <span data-ttu-id="046e8-151">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="046e8-151">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="046e8-152">AllowSelfServicePurchase の状態を表示または設定する</span><span class="sxs-lookup"><span data-stu-id="046e8-152">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="046e8-153">セルフサービス購入で使用できる製品の一覧を表示した後、特定の製品の設定を表示または変更できます。</span><span class="sxs-lookup"><span data-stu-id="046e8-153">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="046e8-154">特定の製品のポリシー設定を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="046e8-154">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="046e8-155">特定の製品のポリシー設定を有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="046e8-155">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="046e8-156">特定の製品のポリシー設定を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="046e8-156">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="046e8-157">AllowSelfServicePurchase を無効にするスクリプトの例</span><span class="sxs-lookup"><span data-stu-id="046e8-157">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="046e8-158">次の例では **、MSCommerce** モジュールをインポートし、アカウントでサインインし、Power Automate の **ProductId** を取得し、その製品の **AllowSelfServicePurchase** を無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="046e8-158">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="046e8-159">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="046e8-159">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="046e8-160">問題</span><span class="sxs-lookup"><span data-stu-id="046e8-160">Problem</span></span>

<span data-ttu-id="046e8-161">次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="046e8-161">You see the following error message:</span></span>

> <span data-ttu-id="046e8-162">HandleError : PolicyId 'AllowSelfServicePurchase', ErrorMessage - 基になる接続が閉じられました: 送信時に予期しないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="046e8-162">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="046e8-163">これは、トランスポート層セキュリティ (TLS) の古いバージョンが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="046e8-163">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="046e8-164">このサービスを接続するには、TLS 1.2 以上を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="046e8-164">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="046e8-165">ソリューション</span><span class="sxs-lookup"><span data-stu-id="046e8-165">Solution</span></span>

<span data-ttu-id="046e8-166">TLS 1.2 へのアップグレード: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="046e8-166">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
