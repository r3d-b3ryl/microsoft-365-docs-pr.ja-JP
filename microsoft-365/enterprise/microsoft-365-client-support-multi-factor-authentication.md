---
title: 'Microsoft 365クライアント アプリのサポート: 多要素認証'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: この記事では、複数要素認証をサポートするプラットフォーム、クライアント、および PowerShell モジュールについてMicrosoft 365。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80ee370526d17d472cd048cd4d89b862e158b631
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927565"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="9309f-103">Microsoft 365クライアント アプリのサポート: 多要素認証</span><span class="sxs-lookup"><span data-stu-id="9309f-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="9309f-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="9309f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9309f-105">サインインに追加レベルのセキュリティを提供するために、クライアントは、次に基づいてユーザー パスワードと別のユーザー検証方法の両方を使用する多要素認証 (MFA) を使用するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="9309f-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and another user verification method based on:</span></span>

- <span data-ttu-id="9309f-106">スマートフォンなど、簡単に複製されない所有物。</span><span class="sxs-lookup"><span data-stu-id="9309f-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="9309f-107">指紋、顔、その他の生体認証属性など、ユーザーが一意で生物学的に持つもの</span><span class="sxs-lookup"><span data-stu-id="9309f-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="9309f-108">多要素認証 [の詳細については、次のページを参照してください](/azure/active-directory/authentication/multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="9309f-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="9309f-109">サポートされているクライアント&プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="9309f-109">Supported clients & platforms</span></span>

<span data-ttu-id="9309f-110">次のクライアントとプラットフォームの最新バージョンでは、多要素認証がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9309f-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="9309f-111">プラットフォームサポートの詳細については、「Microsoft 365のシステム要件」[を参照Microsoft 365。](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="9309f-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="9309f-112">サポートされている PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="9309f-112">Supported PowerShell modules</span></span>

- [<span data-ttu-id="9309f-113">Azure Active DirectoryPowerShell</span><span class="sxs-lookup"><span data-stu-id="9309f-113">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="9309f-114">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="9309f-114">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="9309f-115">SharePointオンライン PowerShell</span><span class="sxs-lookup"><span data-stu-id="9309f-115">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)