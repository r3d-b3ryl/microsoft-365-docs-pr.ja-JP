---
title: 'Microsoft 365クライアント アプリのサポート: 条件付きアクセス'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: この記事では、条件付きアプリケーションをサポートするプラットフォーム、クライアント、および PowerShell モジュールAccess for Microsoft 365。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7b0b65ea25091aad01fd8741f9925f2b545e9c4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904968"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="b948d-103">Microsoft 365クライアント アプリのサポート: 条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="b948d-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="b948d-104">最新の職場では、ユーザーはどこからでもさまざまなデバイスやアプリを使用して組織のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b948d-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="b948d-105">その結果、リソースにアクセスできるユーザーに焦点を当てるだけで十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="b948d-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="b948d-106">組織は、アクセス制御インフラストラクチャでリソースにアクセスする方法と場所もサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b948d-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="b948d-107">デバイスAzure Active Directory、多要素認証ベースの条件付きアクセスを使用すると、この新しい要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="b948d-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="b948d-108">条件付きアクセスは、Azure Active Directoryの機能であり、環境内のアプリへのアクセスに対して、特定の条件に基づいて制御を適用し、中央の場所から管理できます。</span><span class="sxs-lookup"><span data-stu-id="b948d-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="b948d-109">条件付きアクセスの[詳細Azure Active Directoryを参照してください](/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="b948d-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="b948d-110">サポートされているクライアント&プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="b948d-110">Supported clients & platforms</span></span>

<span data-ttu-id="b948d-111">次のクライアントとプラットフォームの最新バージョンでは、条件付きアクセスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b948d-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="b948d-112">プラットフォームサポートの詳細については、「Microsoft 365のシステム要件」[を参照Microsoft 365。](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="b948d-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="b948d-113">サポートされている PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="b948d-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="b948d-114">Azure Active DirectoryPowerShell</span><span class="sxs-lookup"><span data-stu-id="b948d-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="b948d-115">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="b948d-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="b948d-116">SharePointオンライン PowerShell</span><span class="sxs-lookup"><span data-stu-id="b948d-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
