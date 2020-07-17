---
title: サービス暗号化
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
ms.openlocfilehash: 4759cfda13ab5044ddf5980d7e61004e9e7626fa
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024777"
---
# <a name="service-encryption"></a><span data-ttu-id="83458-103">サービス暗号化</span><span class="sxs-lookup"><span data-stu-id="83458-103">Service Encryption</span></span>

<span data-ttu-id="83458-104">ボリュームレベルの暗号化に加えて、Exchange Online、Skype for Business、SharePoint Online、および OneDrive for business では、顧客データを暗号化するためにサービス暗号化も使用されます。</span><span class="sxs-lookup"><span data-stu-id="83458-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="83458-105">サービス暗号化では、2つの主要な管理オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="83458-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="83458-106">Microsoft の管理キー</span><span class="sxs-lookup"><span data-stu-id="83458-106">Microsoft managed keys</span></span>
<span data-ttu-id="83458-107">Microsoft は、サービス暗号化のルートキーを含む、すべての暗号化キーを管理します。</span><span class="sxs-lookup"><span data-stu-id="83458-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="83458-108">このオプションは現在、SharePoint Online と OneDrive for business で使用できます。</span><span class="sxs-lookup"><span data-stu-id="83458-108">This option is currently available in SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="83458-109">現在、このオプションは Exchange Online に対してロールアウトされています。</span><span class="sxs-lookup"><span data-stu-id="83458-109">This option is currently being rolled out for Exchange Online.</span></span> <span data-ttu-id="83458-110">Microsoft の管理キーでは、顧客キーを使用してオンにしない限り、既定のサービス暗号化が提供されます。</span><span class="sxs-lookup"><span data-stu-id="83458-110">Microsoft managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="83458-111">後日、データの削除パスを入力せずに、顧客キーの使用を停止することを決定した場合は、Microsoft のマネージキーを使用してデータが暗号化されたままになります。</span><span class="sxs-lookup"><span data-stu-id="83458-111">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft managed keys.</span></span> <span data-ttu-id="83458-112">データは常にこの既定レベルで暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="83458-112">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="83458-113">顧客キー</span><span class="sxs-lookup"><span data-stu-id="83458-113">Customer Key</span></span>
<span data-ttu-id="83458-114">サービス暗号化で使用するルートキーを指定し、Azure Key Vault を使用してこれらのキーを管理します。</span><span class="sxs-lookup"><span data-stu-id="83458-114">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="83458-115">Microsoft は、その他のすべてのキーを管理します。</span><span class="sxs-lookup"><span data-stu-id="83458-115">Microsoft manages all other keys.</span></span> <span data-ttu-id="83458-116">このオプションは顧客キーと呼ばれ、現在、Exchange Online、SharePoint Online、OneDrive for business で使用できます。</span><span class="sxs-lookup"><span data-stu-id="83458-116">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="83458-117">(以前は BYOK で高度な暗号化と呼ばれています)。</span><span class="sxs-lookup"><span data-stu-id="83458-117">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="83458-118">元のアナウンスについては、「 [Office 365 のお客様の透明性と統制の強化](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="83458-118">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="83458-119">サービス暗号化には複数の利点があります。</span><span class="sxs-lookup"><span data-stu-id="83458-119">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="83458-120">たとえば、顧客キーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="83458-120">For example, Customer Key:</span></span>

- <span data-ttu-id="83458-121">強力な暗号化保護の上に、権限の保護と管理の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="83458-121">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="83458-122">マルチテナントのキー管理をマルチテナントサービスが提供できるようにする顧客キーオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="83458-122">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="83458-123">Windows オペレーティングシステム管理者と、オペレーティングシステムによって保存または処理される顧客データへのアクセスを分離します。</span><span class="sxs-lookup"><span data-stu-id="83458-123">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="83458-124">は、暗号化に関するコンプライアンス要件を持つお客様の要求を満たす Microsoft 365 の能力を向上させます。</span><span class="sxs-lookup"><span data-stu-id="83458-124">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="83458-125">Customer キーを使用すると、社内ハードウェアサービスモジュール (HSM) または Azure Key Vault (AKV) のどちらかを使用して、独自の暗号化キーを生成できます。</span><span class="sxs-lookup"><span data-stu-id="83458-125">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="83458-126">キーの生成方法に関係なく、Office 365 で使用される暗号化キーを制御および管理するのには、AKV を使用します。</span><span class="sxs-lookup"><span data-stu-id="83458-126">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="83458-127">AKV にキーを格納すると、メールボックスのデータまたはファイルを暗号化する keychains のルートとして使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="83458-127">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="83458-128">顧客キーのもう1つの利点は、Microsoft がデータを処理できるようにするためのコントロールです。</span><span class="sxs-lookup"><span data-stu-id="83458-128">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="83458-129">Microsoft を使用してサービスを終了したり、クラウドに格納されているデータの一部を削除したりするなど、Office 365 からのデータを削除する場合は、テクニカルコントロールとして顧客キーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="83458-129">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="83458-130">これにより、Microsoft を含むすべての人がデータにアクセスしたり、データを処理したりすることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="83458-130">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="83458-131">顧客キーが追加されており、Microsoft の担当者によるデータへのアクセスを制御するために使用する、お客様のロックボックスを補完しています。</span><span class="sxs-lookup"><span data-stu-id="83458-131">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="83458-132">Exchange Online、Skype for Business、SharePoint Online、チームサイト、OneDrive for business などの Microsoft 365 用のカスタマーキーを設定する方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83458-132">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="83458-133">顧客キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="83458-133">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="83458-134">顧客キーを設定する</span><span class="sxs-lookup"><span data-stu-id="83458-134">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="83458-135">顧客キーを管理する</span><span class="sxs-lookup"><span data-stu-id="83458-135">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="83458-136">顧客キーまたは可用性キーをロールまたは回転する</span><span class="sxs-lookup"><span data-stu-id="83458-136">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="83458-137">可用性キーについて理解する</span><span class="sxs-lookup"><span data-stu-id="83458-137">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

