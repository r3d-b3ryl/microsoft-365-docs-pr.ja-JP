---
title: 廃止 TLS 1.0 および 1.1 in Office 365 GCC High および DoD
description: Office 365 の GCC High および DoD 環境での TLS 1.1 および1.0 のサポートを中止するために、Microsoft が日付を移行する方法と、TLS 1.2 の使用を準備する方法について説明します。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: 76e9b203e58ba7fa23942ea42810456e3bee377d
ms.sourcegitcommit: 42b618231e9f608f3ae7226a313b0366601d0ea2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158882"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="9369c-103">廃止 TLS 1.0 および 1.1 in Office 365 GCC High および DoD</span><span class="sxs-lookup"><span data-stu-id="9369c-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="9369c-104">概要</span><span class="sxs-lookup"><span data-stu-id="9369c-104">Summary</span></span>

<span data-ttu-id="9369c-105">連邦リスクおよび承認管理プログラム (FedRAMP) に関する最新のコンプライアンス標準に準拠するために、Microsoft Office 365 で廃止トランスポート層セキュリティ (TLS) バージョン1.1 および1.0 を使用して、GCC High および DoD 環境を対象としています。</span><span class="sxs-lookup"><span data-stu-id="9369c-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are deprecating Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="9369c-106">この変更は [、Office 365 で TLS 1.2 の必須の使用を準備するために、](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)Microsoft サポートによって既に発表されています。</span><span class="sxs-lookup"><span data-stu-id="9369c-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="9369c-107">データのセキュリティは重要であり、サービスの使用に影響を与える可能性がある変更については透過的にコミットされています。</span><span class="sxs-lookup"><span data-stu-id="9369c-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="9369c-108">[MICROSOFT TLS 1.0 の実装](https://support.microsoft.com/help/3117336)には既知のセキュリティ上の脆弱性はありませんが、FedRAMP 準拠の標準に対してコミットされたままになります。</span><span class="sxs-lookup"><span data-stu-id="9369c-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="9369c-109">そのため、1.1 年1月 2020 15 日から開始する GCC High および DoD 環境では、Office 365 の TLS および1.0 は廃止されます。</span><span class="sxs-lookup"><span data-stu-id="9369c-109">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="9369c-110">TLS 1.1 および1.0 の依存関係を削除する方法の詳細については、次のホワイトペーパーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9369c-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="9369c-111">TLS 1.0 の問題を解決する</span><span class="sxs-lookup"><span data-stu-id="9369c-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="9369c-112">TLS 1.1 および1.0 に対するこの変更の準備では、代わりに TLS バージョン1.2 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9369c-112">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="9369c-113">詳細については、「 [Office 365 での TLS 1.2 の必須使用の準備](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9369c-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="9369c-114">詳細情報</span><span class="sxs-lookup"><span data-stu-id="9369c-114">More information</span></span>

<span data-ttu-id="9369c-115">2020年1月15日から、GCC High および DoD 環境の Office 365 は TLS 1.1 および1.0 を廃止します。</span><span class="sxs-lookup"><span data-stu-id="9369c-115">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="9369c-116">2020年1月15日までに、クライアントサーバーとブラウザーサーバーのすべての組み合わせで TLS バージョン 1.2 (またはそれ以降のバージョン) を使用して、すべての接続が Office 365 サービスに問題が発生しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9369c-116">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="9369c-117">この場合、クライアントサーバーとブラウザーサーバーの特定の組み合わせに対する更新が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9369c-117">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="9369c-118">2020年1月15日までに、TLS バージョン 1.2 (またはそれ以降のバージョン) に更新しない場合は、Office 365 に接続しようとすると問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="9369c-118">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="9369c-119">また、解決策の一部として、TLS 1.2 (またはそれ以降のバージョン) に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9369c-119">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="9369c-120">次のクライアントは、TLS 1.2 を使用できないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="9369c-120">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="9369c-121">Android 4.3 およびそれ以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="9369c-121">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="9369c-122">Firefox 5.0 およびそれ以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="9369c-122">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="9369c-123">Windows 7 およびそれ以前のバージョンの Internet Explorer 8 ~ 10</span><span class="sxs-lookup"><span data-stu-id="9369c-123">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="9369c-124">Windows Phone 8.0 の Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="9369c-124">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="9369c-125">Safari 6.0.4/OS X 10.8.4 以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="9369c-125">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="9369c-126">Office 365 GCC High および DoD への継続的なアクセスを維持するように、クライアントを更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9369c-126">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="9369c-127">Microsoft Online services への接続の現在の分析には、ほとんどのサービスとエンドポイントが TLS 1.1 および 1.0 1.0 1.1 の使用率が非常に低くなっていることが示されていますが、この変更に関する通知を提供して、影響を受けるクライアントまたはサーバーを必要に応じて更新できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9369c-127">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="9369c-128">ハイブリッドシナリオまたは Active Directory フェデレーションサービス (AD FS) に対してオンプレミスのインフラストラクチャを使用している場合は、TLS 1.2 (またはそれ以降のバージョン) を使用する受信と送信の両方の接続をインフラストラクチャがサポートできることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9369c-128">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="9369c-129">TLS 1.2 を使用できないクライアントを使用した場合に発生する可能性のある停止に加えて、TLS 1.1 および1.0 を削除すると、次の Microsoft 製品を使用することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="9369c-129">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="9369c-130">Lync phone</span><span class="sxs-lookup"><span data-stu-id="9369c-130">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="9369c-131">関連情報</span><span class="sxs-lookup"><span data-stu-id="9369c-131">References</span></span>

<span data-ttu-id="9369c-132">次のサポート記事には、クライアントが TLS 1.2 を使用していることを確認するためのガイダンスと参考情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="9369c-132">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="9369c-133">Office 365 での TLS 1.2 の必須使用の準備</span><span class="sxs-lookup"><span data-stu-id="9369c-133">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
