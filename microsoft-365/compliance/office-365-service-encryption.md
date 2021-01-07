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
description: '概要: Microsoft Office 365 のデータ復元について説明します。'
ms.openlocfilehash: fbd2672986046a4f6d25c47b011eaef0a87d90e1
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777052"
---
# <a name="service-encryption"></a><span data-ttu-id="34777-103">サービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="34777-103">Service Encryption</span></span>

<span data-ttu-id="34777-104">ボリューム レベルの暗号化に加えて、Exchange Online、Skype for Business、SharePoint Online、および OneDrive for Business は、顧客データの暗号化にサービス暗号化も使用します。</span><span class="sxs-lookup"><span data-stu-id="34777-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="34777-105">サービスの暗号化では、次の 2 つの主要な管理オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34777-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="34777-106">Microsoft が管理するキー</span><span class="sxs-lookup"><span data-stu-id="34777-106">Microsoft-managed keys</span></span>
<span data-ttu-id="34777-107">Microsoft では、サービス暗号化のルート キーを含むすべての暗号化キーを管理しています。</span><span class="sxs-lookup"><span data-stu-id="34777-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="34777-108">このオプションは現在、Exchange Online、SharePoint Online、OneDrive for Business で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="34777-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="34777-109">Microsoft で管理されるキーは、カスタマー キーを使用してオンボードしない限り、既定のサービス暗号化を提供します。</span><span class="sxs-lookup"><span data-stu-id="34777-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="34777-110">後日、データ消去パスに従わずに顧客キーの使用を停止する場合、データは Microsoft が管理するキーを使用して暗号化されたままとなります。</span><span class="sxs-lookup"><span data-stu-id="34777-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="34777-111">データは、少なくともこの既定のレベルで常に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="34777-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="34777-112">顧客キー</span><span class="sxs-lookup"><span data-stu-id="34777-112">Customer Key</span></span>
<span data-ttu-id="34777-113">サービスの暗号化で使用するルート キーを指定し、Azure Key Vault を使用してこれらのキーを管理します。</span><span class="sxs-lookup"><span data-stu-id="34777-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="34777-114">Microsoft は、他のすべてのキーを管理します。</span><span class="sxs-lookup"><span data-stu-id="34777-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="34777-115">このオプションは顧客キーと呼ばされ、現在 Exchange Online、SharePoint Online、OneDrive for Business で使用できます。</span><span class="sxs-lookup"><span data-stu-id="34777-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="34777-116">(以前は BYOK を使用した Advanced Encryption と呼ばばていました。</span><span class="sxs-lookup"><span data-stu-id="34777-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="34777-117">最初 [のお知らせについては、365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) Officeの透明性とコントロールの強化に関するページをご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="34777-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="34777-118">サービスの暗号化には、次の複数の利点があります。</span><span class="sxs-lookup"><span data-stu-id="34777-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="34777-119">BitLocker の上に保護の層を追加します。</span><span class="sxs-lookup"><span data-stu-id="34777-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="34777-120">Windows オペレーティング システム管理者が、オペレーティング システムによって保存または処理されたアプリケーション データへのアクセスから分離します。</span><span class="sxs-lookup"><span data-stu-id="34777-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="34777-121">マルチテナント サービスがテナント単位のキー管理を提供できる顧客キー オプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="34777-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="34777-122">暗号化に関する特定のコンプライアンス要件を持つお客様の要求に応える Microsoft 365 の機能を強化します。</span><span class="sxs-lookup"><span data-stu-id="34777-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="34777-123">顧客キーを使用すると、オンプレミスのハードウェア サービス モジュール (VAULT) または Azure Key Vault (A VAULT) のいずれかを使用して、独自の暗号化キーを生成できます。</span><span class="sxs-lookup"><span data-stu-id="34777-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="34777-124">キーの生成方法に関係なく、ARK を使用して、365 で使用される暗号化キーをOfficeします。</span><span class="sxs-lookup"><span data-stu-id="34777-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="34777-125">キーを ARK に保存したら、メールボックスのデータまたはファイルを暗号化するキーチェーンのルートとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="34777-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="34777-126">顧客キーのもう 1 つの利点は、Microsoft がデータを処理する機能を制御する方法です。</span><span class="sxs-lookup"><span data-stu-id="34777-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="34777-127">Office 365 からデータを削除する場合 (Microsoft とのサービスを終了する場合や、クラウドに保存されているデータの一部を削除する場合など) は、その操作を行い、テクニカル コントロールとして顧客キーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34777-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="34777-128">データを削除すると、Microsoft を含む誰もデータにアクセスしたり処理したりしなけずに行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="34777-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="34777-129">カスタマー キーは、Microsoft の担当者によるデータへのアクセスを制御するために使用するカスタマー ロックボックスに加えて補完的です。</span><span class="sxs-lookup"><span data-stu-id="34777-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="34777-130">Microsoft 365 for Exchange Online、Skype for Business、SharePoint Online (チーム サイト、OneDrive for Business を含む) のカスタマー キーをセットアップする方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34777-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="34777-131">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="34777-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="34777-132">顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="34777-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="34777-133">顧客キーの管理</span><span class="sxs-lookup"><span data-stu-id="34777-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="34777-134">顧客キーまたは可用性キーをロールまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="34777-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="34777-135">可用性キーを理解する</span><span class="sxs-lookup"><span data-stu-id="34777-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

