---
title: Office 365 でのサービスの暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: Microsoft Office 365 のサービス層でのデータ暗号化について説明します。'
ms.openlocfilehash: fb6bf87fbd51bcb4383e9eb595ef11f081989d86
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211944"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="72df5-103">Office 365 でのサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="72df5-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="72df5-104">BitLocker をボリュームレベルの暗号化に使用することに加えて、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、および Teams でも、サービス暗号化を使用して顧客データを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="72df5-104">In addition to using BitLocker for volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="72df5-105">サービス暗号化では、2つの主要な管理オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="72df5-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="72df5-106">Microsoft は、すべての暗号化キーを管理します。</span><span class="sxs-lookup"><span data-stu-id="72df5-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="72df5-107">このオプションは現在、SharePoint Online、OneDrive for Business、Skype for business、および Teams のチャットで利用できます。</span><span class="sxs-lookup"><span data-stu-id="72df5-107">This option is currently available in SharePoint Online, OneDrive for Business, Skype for Business, and Teams chats.</span></span> <span data-ttu-id="72df5-108">データは、Microsoft が管理するキーを使用して、既定で暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="72df5-108">Your data is encrypted by default with Microsoft-managed keys.</span></span>

- <span data-ttu-id="72df5-109">組織がルートキーを提供します。</span><span class="sxs-lookup"><span data-stu-id="72df5-109">Your organization supplies the root keys.</span></span> <span data-ttu-id="72df5-110">これらのキーは、Azure Key Vault を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="72df5-110">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="72df5-111">このオプションは、顧客キーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="72df5-111">This option is called Customer Key.</span></span> <span data-ttu-id="72df5-112">顧客キーは現在、Exchange Online、SharePoint Online、OneDrive for business、Skype for Business、および Teams ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="72df5-112">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="72df5-113">顧客キーを使用する場合、これらのキーは Microsoft が管理するキーを置き換えてデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="72df5-113">If you use Customer Key, these keys replace Microsoft-managed keys to encrypt your data.</span></span>

<span data-ttu-id="72df5-114">どのオプションを選択しても、サービス暗号化には複数の利点があります。</span><span class="sxs-lookup"><span data-stu-id="72df5-114">Whatever option you choose, service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="72df5-115">承認済みユーザーによって要求されたデータを取得して復号化するために、ユーザー認証を適用します。</span><span class="sxs-lookup"><span data-stu-id="72df5-115">Enforces user authentication to retrieve and decrypt data requested by an authorized user.</span></span>

- <span data-ttu-id="72df5-116">Windows オペレーティングシステム管理者と、オペレーティングシステムによって保存または処理される顧客データへのアクセスを分離します。</span><span class="sxs-lookup"><span data-stu-id="72df5-116">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="72df5-117">暗号化に関するコンプライアンス要件を持つお客様の要求を満たす Office 365 の能力を向上させます。</span><span class="sxs-lookup"><span data-stu-id="72df5-117">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="72df5-118">Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、および Teams の各ファイルに対して Office 365 の顧客キーを設定する方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72df5-118">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files, see these articles:</span></span>

- [<span data-ttu-id="72df5-119">Office 365 での顧客キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="72df5-119">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="72df5-120">Office 365 の顧客キーを設定する</span><span class="sxs-lookup"><span data-stu-id="72df5-120">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="72df5-121">Office 用の顧客キーの管理365</span><span class="sxs-lookup"><span data-stu-id="72df5-121">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="72df5-122">顧客キーまたは可用性キーをロールまたは回転する</span><span class="sxs-lookup"><span data-stu-id="72df5-122">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="72df5-123">可用性キーについて理解する</span><span class="sxs-lookup"><span data-stu-id="72df5-123">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
