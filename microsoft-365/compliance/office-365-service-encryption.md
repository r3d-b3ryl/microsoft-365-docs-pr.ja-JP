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
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: Microsoft Office 365 のデータ復元性について理解します。'
ms.openlocfilehash: ec7f794a62a910fadaece890cf73451644d44109
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071114"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="3185d-103">Office 365 でのサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="3185d-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="3185d-104">ボリュームレベルの暗号化に加えて、Exchange Online、Skype for Business、SharePoint Online、および OneDrive for business では、顧客データを暗号化するためにサービス暗号化も使用されます。</span><span class="sxs-lookup"><span data-stu-id="3185d-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="3185d-105">サービス暗号化では、2つの主要な管理オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3185d-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="3185d-106">Microsoft は、すべての暗号化キーを管理します。</span><span class="sxs-lookup"><span data-stu-id="3185d-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="3185d-107">(現在、このオプションは SharePoint Online、OneDrive for Business、Skype for business で利用できます)。</span><span class="sxs-lookup"><span data-stu-id="3185d-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="3185d-108">お客様は、サービスの暗号化に使用されるルートキーを提供し、お客様は Azure Key Vault を使用してこれらのキーを管理します。</span><span class="sxs-lookup"><span data-stu-id="3185d-108">The customer supplies root keys used with service encryption and the customer manages these keys using Azure Key Vault.</span></span> <span data-ttu-id="3185d-109">Microsoft は、その他のすべてのキーを管理します。</span><span class="sxs-lookup"><span data-stu-id="3185d-109">Microsoft manages all other keys.</span></span> <span data-ttu-id="3185d-110">このオプションは顧客キーと呼ばれ、現在、Exchange Online、SharePoint Online、OneDrive for business で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3185d-110">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="3185d-111">(以前は BYOK で高度な暗号化と呼ばれています)。</span><span class="sxs-lookup"><span data-stu-id="3185d-111">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="3185d-112">元のアナウンスについては、「 [Office 365 のお客様の透明性と統制の強化](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3185d-112">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="3185d-113">サービス暗号化には複数の利点があります。</span><span class="sxs-lookup"><span data-stu-id="3185d-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="3185d-114">たとえば、顧客キーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3185d-114">For example, Customer Key:</span></span>

- <span data-ttu-id="3185d-115">強力な暗号化保護の上に、権限の保護と管理の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="3185d-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="3185d-116">マルチテナントのキー管理をマルチテナントサービスが提供できるようにする顧客キーオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3185d-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="3185d-117">Windows オペレーティングシステム管理者と、オペレーティングシステムによって保存または処理される顧客データへのアクセスを分離します。</span><span class="sxs-lookup"><span data-stu-id="3185d-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="3185d-118">暗号化に関するコンプライアンス要件を持つお客様の要求を満たす Office 365 の能力を向上させます。</span><span class="sxs-lookup"><span data-stu-id="3185d-118">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="3185d-119">カスタマー キー</span><span class="sxs-lookup"><span data-stu-id="3185d-119">Customer Key</span></span>

<span data-ttu-id="3185d-120">Customer キーを使用すると、社内ハードウェアサービスモジュール (HSM) または Azure Key Vault (AKV) のどちらかを使用して、独自の暗号化キーを生成できます。</span><span class="sxs-lookup"><span data-stu-id="3185d-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="3185d-121">キーの生成方法に関係なく、Office 365 で使用される暗号化キーを制御および管理するのには、AKV を使用します。</span><span class="sxs-lookup"><span data-stu-id="3185d-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="3185d-122">AKV にキーを格納すると、メールボックスのデータまたはファイルを暗号化する keychains のルートとして使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3185d-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="3185d-123">顧客キーのもう1つの利点は、Microsoft がデータを処理できるようにするためのコントロールです。</span><span class="sxs-lookup"><span data-stu-id="3185d-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="3185d-124">Microsoft を使用してサービスを終了したり、クラウドに格納されているデータの一部を削除したりするなど、Office 365 からのデータを削除する場合は、テクニカルコントロールとして顧客キーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3185d-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="3185d-125">これにより、Microsoft を含むすべての人がデータにアクセスしたり、データを処理したりすることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="3185d-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="3185d-126">顧客キーが追加されており、Microsoft の担当者によるデータへのアクセスを制御するために使用する、お客様のロックボックスを補完しています。</span><span class="sxs-lookup"><span data-stu-id="3185d-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="3185d-127">Exchange Online、Skype for Business、SharePoint Online、チームサイト、OneDrive for business などの Office 365 の顧客キーを設定する方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3185d-127">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="3185d-128">Office 365 での顧客キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="3185d-128">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="3185d-129">Office 365 の顧客キーを設定する</span><span class="sxs-lookup"><span data-stu-id="3185d-129">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="3185d-130">Office 用の顧客キーの管理365</span><span class="sxs-lookup"><span data-stu-id="3185d-130">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="3185d-131">顧客キーまたは可用性キーをロールまたは回転する</span><span class="sxs-lookup"><span data-stu-id="3185d-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="3185d-132">可用性キーについて理解する</span><span class="sxs-lookup"><span data-stu-id="3185d-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 
