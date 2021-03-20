---
title: Exchange Online がメールの機密情報をセキュリティで保護する方法
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Microsoft 365 のセキュリティ、プライバシー、コンプライアンス情報を提供する Office 365 セキュリティ センターに加えて、Microsoft がデータセンターに保存するシークレットを保護する方法を知りたい場合があります。 分散キー マネージャー (DKM) というテクノロジを使用します。
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906963"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="27d91-104">Exchange Online がメールの機密情報をセキュリティで保護する方法</span><span class="sxs-lookup"><span data-stu-id="27d91-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="27d91-105">この記事では、Microsoft がデータセンターで電子メール シークレットをセキュリティで保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="27d91-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="27d91-106">お客様が提供する秘密情報をセキュリティで保護する方法</span><span class="sxs-lookup"><span data-stu-id="27d91-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="27d91-107">Office 365 のセキュリティ、プライバシー、コンプライアンス情報を提供する [Office 365](./get-started-with-service-trust-portal.md)セキュリティ センターに加えて、Microsoft がデータセンターで提供するシークレットを保護する方法を知りたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="27d91-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](./get-started-with-service-trust-portal.md), you might want to know how Microsoft helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="27d91-108">分散キー マネージャー (DKM) というテクノロジを使用します。</span><span class="sxs-lookup"><span data-stu-id="27d91-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="27d91-109">[分散キー マネージャー](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) は、一連のシークレット キーを使用して情報を暗号化および復号化するクライアント側の機能です。</span><span class="sxs-lookup"><span data-stu-id="27d91-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="27d91-110">DKM で暗号化されたデータを復号化するには、Active Directory ドメイン サービスの特定のセキュリティ グループのメンバーだけがこれらのキーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="27d91-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="27d91-111">Exchange Online では Exchange プロセスの実行に使用する特定のサービス アカウントだけが、そのセキュリティ グループに属します。</span><span class="sxs-lookup"><span data-stu-id="27d91-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="27d91-112">データセンター内の標準運用手順の一環として、このセキュリティ グループに属する資格情報は人間には付与されないため、人間はだれもこれらの機密情報を解読できるキーにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="27d91-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="27d91-113">デバッグ、トラブルシューティング、または監査の目的で、データセンター管理者は、セキュリティ グループの一部である一時的な資格情報を取得するために、管理者特権でのアクセスを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27d91-113">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group.</span></span> <span data-ttu-id="27d91-114">このプロセスでは、複数のレベルの法的承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="27d91-114">This process requires multiple levels of legal approval.</span></span> <span data-ttu-id="27d91-115">アクセスが許可されている場合、すべてのアクティビティがログに記録され、監査されます。</span><span class="sxs-lookup"><span data-stu-id="27d91-115">If access is granted, all activity is logged and audited.</span></span> <span data-ttu-id="27d91-116">さらに、アクセスは、自動的に期限切れになる一定の間隔でのみ付与されます。</span><span class="sxs-lookup"><span data-stu-id="27d91-116">In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="27d91-117">特別な保護のために、DKM テクノロジには自動キー ロールオーバーとアーカイブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="27d91-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="27d91-118">これにより、同じキーに無期限に依存することなく、古いコンテンツに引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="27d91-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="27d91-119">Exchange Online は DKM をどこで利用しますか?</span><span class="sxs-lookup"><span data-stu-id="27d91-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="27d91-120">Microsoft では、 [分散キー マネージャーを](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) 使用して Exchange Online データセンター内のシークレットを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="27d91-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="27d91-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="27d91-121">For example:</span></span>
  
- <span data-ttu-id="27d91-122">接続されたアカウントの電子メール アカウント資格情報。</span><span class="sxs-lookup"><span data-stu-id="27d91-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="27d91-123">接続されたアカウントは、アプリ、Gmail、Yahoo などのHotmailサード パーティのアカウントです。</span><span class="sxs-lookup"><span data-stu-id="27d91-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="27d91-124">メール アカウント。</span><span class="sxs-lookup"><span data-stu-id="27d91-124">mail accounts.</span></span>

- <span data-ttu-id="27d91-125">顧客キー。</span><span class="sxs-lookup"><span data-stu-id="27d91-125">Customer key.</span></span> <span data-ttu-id="27d91-126">顧客キーで [サービス暗号化を使用している場合](customer-key-overview.md)は [、Azure Key Vault](/azure/key-vault/key-vault-whatis) を使用してシークレットを保護します。</span><span class="sxs-lookup"><span data-stu-id="27d91-126">If you are using [Service encryption with Customer Key](customer-key-overview.md), you'll use [Azure Key Vault](/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>

## <a name="related-topics"></a><span data-ttu-id="27d91-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="27d91-127">Related topics</span></span>

[<span data-ttu-id="27d91-128">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="27d91-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="27d91-129">暗号化についてのテクニカル リファレンスの詳細</span><span class="sxs-lookup"><span data-stu-id="27d91-129">Technical reference details about encryption</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="27d91-130">セキュリティ コンプライアンス センター &amp; のサービス アシュアランス</span><span class="sxs-lookup"><span data-stu-id="27d91-130">Service assurance in the Security &amp; Compliance Center</span></span>](./service-assurance.md)
