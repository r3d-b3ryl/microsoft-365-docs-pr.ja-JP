---
title: サービスの暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: データの復元性についてMicrosoft Office 365。'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058550"
---
# <a name="service-encryption"></a><span data-ttu-id="3eefc-103">サービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="3eefc-103">Service Encryption</span></span>

<span data-ttu-id="3eefc-104">ボリューム レベルの暗号化の使用に加えて、Exchange Online、Microsoft Teams、SharePoint Online、および OneDrive for Business サービス暗号化を使用して顧客データを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="3eefc-104">In addition to using volume-level encryption, Exchange Online, Microsoft Teams, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="3eefc-105">サービスの暗号化では、次の 2 つのキー管理オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3eefc-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="3eefc-106">Microsoft が管理するキー</span><span class="sxs-lookup"><span data-stu-id="3eefc-106">Microsoft-managed keys</span></span>
<span data-ttu-id="3eefc-107">Microsoft は、サービス暗号化のルート キーを含むすべての暗号化キーを管理します。</span><span class="sxs-lookup"><span data-stu-id="3eefc-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="3eefc-108">このオプションは現在、オンライン、オンライン、Exchange Online、SharePointに対してOneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="3eefc-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="3eefc-109">Microsoft 管理キーは、顧客キーを使用してオンボードを決定しない限り、既定のサービス暗号化を提供します。</span><span class="sxs-lookup"><span data-stu-id="3eefc-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="3eefc-110">後日、データ削除パスに従わずに顧客キーの使用を停止する場合、データは Microsoft 管理キーを使用して暗号化されたままです。</span><span class="sxs-lookup"><span data-stu-id="3eefc-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="3eefc-111">データは、少なくともこの既定のレベルで常に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="3eefc-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="3eefc-112">顧客キー</span><span class="sxs-lookup"><span data-stu-id="3eefc-112">Customer Key</span></span>
<span data-ttu-id="3eefc-113">サービス暗号化で使用されるルート キーを指定し、Azure Key Vault を使用してこれらのキーを管理します。</span><span class="sxs-lookup"><span data-stu-id="3eefc-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="3eefc-114">Microsoft は、他のすべてのキーを管理します。</span><span class="sxs-lookup"><span data-stu-id="3eefc-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="3eefc-115">このオプションは Customer Key と呼ばされ、現在、オンライン、Exchange Online、SharePoint、およびOneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="3eefc-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="3eefc-116">(以前は BYOK による高度な暗号化と呼ばば)</span><span class="sxs-lookup"><span data-stu-id="3eefc-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="3eefc-117">元[のアナウンスについては、「ユーザーの透明性とコントロールOffice 365強化](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3eefc-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="3eefc-118">サービスの暗号化には、次の複数の利点があります。</span><span class="sxs-lookup"><span data-stu-id="3eefc-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="3eefc-119">ユーザーの上に追加の保護層を提供BitLocker。</span><span class="sxs-lookup"><span data-stu-id="3eefc-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="3eefc-120">オペレーティング システム管理者Windows、オペレーティング システムによって保存または処理されるアプリケーション データへのアクセスから分離します。</span><span class="sxs-lookup"><span data-stu-id="3eefc-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="3eefc-121">テナントごとのキー管理を提供するマルチテナント サービスを有効にする顧客キー オプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3eefc-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="3eefc-122">暗号化に関する特定のMicrosoft 365を持つ顧客の要求を満たす機能を強化します。</span><span class="sxs-lookup"><span data-stu-id="3eefc-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="3eefc-123">顧客キーを使用すると、オンプレミスのハードウェア サービス モジュール (HSM) または Azure Key Vault (AKV) のいずれかを使用して、独自の暗号化キーを生成できます。</span><span class="sxs-lookup"><span data-stu-id="3eefc-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="3eefc-124">キーの生成方法に関係なく、AKV を使用して、ユーザーが使用する暗号化キーを制御および管理Office 365。</span><span class="sxs-lookup"><span data-stu-id="3eefc-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="3eefc-125">キーを AKV に格納すると、メールボックス データまたはファイルを暗号化するキーチェーンのルートとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="3eefc-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="3eefc-126">顧客キーのもう 1 つの利点は、Microsoft がデータを処理する機能を制御することです。</span><span class="sxs-lookup"><span data-stu-id="3eefc-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="3eefc-127">microsoft でサービスを終了する場合や、クラウドに保存されているデータの一部を削除する場合など、Office 365 からデータを削除する場合は、テクニカル コントロールとしてカスタマー キーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3eefc-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="3eefc-128">データを削除すると、Microsoft を含む誰もデータにアクセスまたは処理できます。</span><span class="sxs-lookup"><span data-stu-id="3eefc-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="3eefc-129">顧客キーは、Microsoft 担当者によるデータへのアクセスを制御するために使用する顧客ロックボックスに加えて補完的です。</span><span class="sxs-lookup"><span data-stu-id="3eefc-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="3eefc-130">Microsoft 365、Microsoft Teams、SharePoint Exchange Online Online (チーム サイト、OneDrive for Business など) の顧客キーを設定する方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3eefc-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Microsoft Teams, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="3eefc-131">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="3eefc-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="3eefc-132">顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="3eefc-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="3eefc-133">顧客キーの管理</span><span class="sxs-lookup"><span data-stu-id="3eefc-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="3eefc-134">顧客キーまたは可用性キーをロールまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="3eefc-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="3eefc-135">可用性キーについて</span><span class="sxs-lookup"><span data-stu-id="3eefc-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
