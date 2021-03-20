---
title: 'Microsoft 365 クライアント アプリのサポート: シングル Sign-On'
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
description: この記事では、Microsoft 365 のシングル サインオンをサポートするプラットフォーム、クライアント、および PowerShell モジュールについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63090e1284bda39fe2d79c80b829891e867d2365
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904908"
---
# <a name="microsoft-365-client-app-support-single-sign-on"></a><span data-ttu-id="0db69-103">Microsoft 365 クライアント アプリのサポート: シングル Sign-On</span><span class="sxs-lookup"><span data-stu-id="0db69-103">Microsoft 365 Client App Support: Single Sign-On</span></span>

<span data-ttu-id="0db69-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="0db69-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0db69-105">シングル サインオン (SSO) は、ユーザーが Azure Active Directory のアプリケーションにサインオンするときにセキュリティと利便性を向上します。</span><span class="sxs-lookup"><span data-stu-id="0db69-105">Single sign-on (SSO) adds security and convenience when your users sign-on to applications in Azure Active Directory.</span></span> <span data-ttu-id="0db69-106">シングル サインオンでは、ユーザーは 1 つのアカウントで 1 回サインインして、オンプレミスの Active Directory ドメイン サービス (AD DS) ドメインに参加しているデバイス、サービスとしてのソフトウェア (SaaS) アプリケーション、および Web アプリケーションにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0db69-106">With single sign-on, users sign in once with one account to access on-premises Active Directory Domain Services (AD DS) domain-joined devices, software as a service (SaaS) applications, and web applications.</span></span>

<span data-ttu-id="0db69-107">シングル サインオンの [詳細を参照してください](/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="0db69-107">Learn more about [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="0db69-108">サポートされているクライアント&プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="0db69-108">Supported clients & platforms</span></span>

<span data-ttu-id="0db69-109">次のクライアントとプラットフォームの最新バージョンでは、シングル サインオンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0db69-109">The latest versions of the following clients and platforms support single sign-on.</span></span> <span data-ttu-id="0db69-110">Microsoft 365 でのプラットフォームサポートの詳細については [、「Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)のシステム要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0db69-110">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Single sign-on services support table](../includes/microsoft-365-client-support-single-sign-on-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="0db69-111">サポートされている PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="0db69-111">Supported PowerShell modules</span></span>

- [<span data-ttu-id="0db69-112">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="0db69-112">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="0db69-113">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="0db69-113">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="0db69-114">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="0db69-114">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
