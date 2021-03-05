---
title: Microsoft 365 GCC High および DoD で TLS 1.0 および 1.1 を無効にする
description: Microsoft 365 の GCC High および DoD 環境での TLS 1.1 と 1.0 のサポートを無効にする方法について説明します。
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: d4da76268791e36bd01b5d6f6140fd52c70b3b4a
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454196"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a><span data-ttu-id="4f8a0-103">Microsoft 365 GCC High および DoD で TLS 1.0 および 1.1 を無効にする</span><span class="sxs-lookup"><span data-stu-id="4f8a0-103">Disabling TLS 1.0 and 1.1 in Microsoft 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="4f8a0-104">要約</span><span class="sxs-lookup"><span data-stu-id="4f8a0-104">Summary</span></span>

<span data-ttu-id="4f8a0-105">連邦リスクおよび承認管理プログラム (FedRAMP) の最新のコンプライアンス基準に準拠するために、Microsoft 365 for GCC High および DoD 環境では、トランスポート層セキュリティ (TLS) バージョン 1.1 および 1.0 を無効にします。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="4f8a0-106">この変更は、Microsoft サポートを通じて [、365 での TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須使用の準備でOfficeされました。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="4f8a0-107">データのセキュリティは重要であり、サービスの使用に影響を与える可能性のある変更に関する透明性に取り組む必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="4f8a0-108">Microsoft [TLS 1.0](https://support.microsoft.com/help/3117336) の実装には既知のセキュリティの脆弱性は存在しますが、FedRAMP コンプライアンス標準に引き続き取り組む必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="4f8a0-109">そのため、2020 年 1 月 15 日に GCC High 環境および DoD 環境で Microsoft 365 で TLS 1.1 および 1.0 を無効にしました。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-109">Therefore, we disabled TLS 1.1 and 1.0 in Microsoft 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="4f8a0-110">TLS 1.1 と 1.0 の依存関係を削除する方法については、次のホワイト ペーパーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="4f8a0-111">TLS 1.0 の問題の解決</span><span class="sxs-lookup"><span data-stu-id="4f8a0-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a><span data-ttu-id="4f8a0-112">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4f8a0-112">More information</span></span>

<span data-ttu-id="4f8a0-113">2020 年 1 月 15 日から、GCC High 環境および DoD 環境の Microsoft 365 は TLS 1.1 と 1.0 を無効にします。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-113">Starting on January 15, 2020, Microsoft 365 in the GCC High and DoD environments will disable TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="4f8a0-114">2020 年 1 月 15 日までには、クライアント サーバーとブラウザー サーバーのすべての組み合わせで TLS バージョン 1.2 (または以降のバージョン) を使用して、Microsoft 365 への問題なくすべての接続を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-114">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Microsoft 365.</span></span> <span data-ttu-id="4f8a0-115">これには、クライアント サーバーとブラウザー サーバーの特定の組み合わせに対する更新が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-115">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="4f8a0-116">SharePoint と OneDrive の場合は、TLS 1.2 をサポートするために .NET を更新して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-116">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="4f8a0-117">詳細については、「クライアントで [TLS 1.2 を有効にする方法」を参照してください](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-117">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

<span data-ttu-id="4f8a0-118">クライアント コンピューターを更新して、365 GCC High および DoD に対する中断Officeアクセスを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-118">You must update your client computers to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="4f8a0-119">TLS 1.0 または TLS 1.1 を使用して Microsoft 365 API を呼び出すアプリケーションを更新して、TLS 1.2 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-119">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="4f8a0-120">.NET 4.5 の既定値は TLS 1.1 です。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-120">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="4f8a0-121">.NET 構成を更新するには、「クライアントでトランスポート層セキュリティ [(TLS) 1.2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)を有効にする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-121">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span> <span data-ttu-id="4f8a0-122">詳細については [、「365 の TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須使用の準備」を参照Officeしてください。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-122">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="4f8a0-123">次のクライアント アプリケーションでは TLS 1.2 を使用できないことがわかっています。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-123">We know that the following client applications cannot use TLS 1.2:</span></span>

- <span data-ttu-id="4f8a0-124">Android 4.3 およびそれ以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="4f8a0-124">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="4f8a0-125">Firefox 5.0 およびそれ以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="4f8a0-125">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="4f8a0-126">Internet Explorer 8 7 以前のバージョンの場合は、Internet Explorer 8-10 を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-126">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="4f8a0-127">Internet Explorer 10 on Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="4f8a0-127">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="4f8a0-128">Safari 6.0.4/OS X 10.8.4 以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="4f8a0-128">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="4f8a0-129">Microsoft Online サービスへの接続の現在の分析では、ほとんどのサービスとエンドポイントで TLS 1.1 と 1.0 の使用状況はほとんど表示されませんが、TLS 1.1 および 1.0 のサポートが終了する前に、必要に応じて影響を受けるクライアントまたはサーバーを更新できるよう、この変更に関する通知を提供しています。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we're providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="4f8a0-130">ハイブリッド シナリオまたは Active Directory フェデレーション サービス (AD FS) にオンプレミス インフラストラクチャを使用している場合は、TLS 1.2 (または以降のバージョン) を使用する受信接続と送信接続の両方をインフラストラクチャでサポートできます。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="4f8a0-131">TLS 1.2 を使用できない一覧のクライアントを使用する場合に発生する可能性がある機能停止に加えて、TLS 1.1 と 1.0 を削除すると、次の Microsoft 製品を使用できません。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="4f8a0-132">Lync 電話</span><span class="sxs-lookup"><span data-stu-id="4f8a0-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="4f8a0-133">関連情報</span><span class="sxs-lookup"><span data-stu-id="4f8a0-133">References</span></span>

<span data-ttu-id="4f8a0-134">クライアントが TLS 1.2 を使用している場合のガイダンスと参照については、「Office [365 での TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須使用の準備」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f8a0-134">For guidance and references to help make sure that your clients are using TLS 1.2, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
