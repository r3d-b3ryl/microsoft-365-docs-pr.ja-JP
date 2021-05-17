---
title: 無駄のないポップアウトを使用して、メール メッセージの読み取り時に使用されるメモリを削減する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: この記事では、リーン ポップアウトを使用して Web 上のメッセージダウンロードのパフォーマンスを向上Outlook説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925258"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="ec1e5-103">無駄のないポップアウトを使用して、メール メッセージの読み取り時に使用されるメモリを削減する</span><span class="sxs-lookup"><span data-stu-id="ec1e5-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="ec1e5-104">この記事では、Web 上のメッセージ ダウンロードのパフォーマンスを向上Outlook説明します。</span><span class="sxs-lookup"><span data-stu-id="ec1e5-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="ec1e5-105">この記事は、プロジェクトのネットワーク[計画とパフォーマンスの調整Office 365](./network-planning-and-performance.md)です。</span><span class="sxs-lookup"><span data-stu-id="ec1e5-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
  
<span data-ttu-id="ec1e5-106">Office 365 のグローバル管理者は、Microsoft Edge または Internet Explorer で特定の電子メール メッセージの小規模でメモリ負荷の少ないバージョンのリーン ポップアウトを配信するために、web 上で Outlook を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ec1e5-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="ec1e5-107">リーン ポップアウトが web 上のOutlook構成されている場合、パフォーマンスを最適化するサーバー側レンダリング コンポーネントが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="ec1e5-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec1e5-108">2018 年 3 月の現在、情報権利管理 (IRM) などの使用権限の制限を指定するメッセージでは、リーン ポップアウトを使用できません。</span><span class="sxs-lookup"><span data-stu-id="ec1e5-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="ec1e5-109">これらの機能はメイン ウィンドウで引き続き機能しますが、リーン ポップアウトでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="ec1e5-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="ec1e5-110">Outlook アドイン</span><span class="sxs-lookup"><span data-stu-id="ec1e5-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="ec1e5-111">Skype for Businessプレゼンス</span><span class="sxs-lookup"><span data-stu-id="ec1e5-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="ec1e5-112">組織内のすべてのユーザーにリーン ポップアウトをOffice 365するには</span><span class="sxs-lookup"><span data-stu-id="ec1e5-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="ec1e5-113">[Connect PowerShell をExchange Onlineする方法について説明します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ec1e5-113">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
2. <span data-ttu-id="ec1e5-114">次のように、LeanPopoutEnabled パラメーターを使用して [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ec1e5-114">Run the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="ec1e5-115">たとえば、組織内のすべてのユーザーに対してリーン ポップアウトを有効にするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec1e5-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="ec1e5-116">組織内のすべてのユーザーに対してリーン ポップアウトを無効にするには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec1e5-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```