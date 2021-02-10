---
title: 365 GCC High および DoD で TLS 1.0 Office 1.1 を無効にする
description: Microsoft が Microsoft 365 の GCC High および DoD 環境での TLS 1.1 および 1.0 のサポートを無効にする方法について説明します。
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
ms.openlocfilehash: 006f81ee5b17baca4f42a78c5a87a59e8e90648f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166442"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="1dbef-103">365 GCC High および DoD で TLS 1.0 Office 1.1 を無効にする</span><span class="sxs-lookup"><span data-stu-id="1dbef-103">Disabling TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="1dbef-104">概要</span><span class="sxs-lookup"><span data-stu-id="1dbef-104">Summary</span></span>

<span data-ttu-id="1dbef-105">Federal Risk and Authorization Management Program (FedRAMP) の最新のコンプライアンス基準に準拠するために、Microsoft 365 for GCC High および DoD 環境ではトランスポート層セキュリティ (TLS) バージョン 1.1 および 1.0 を無効にします。</span><span class="sxs-lookup"><span data-stu-id="1dbef-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="1dbef-106">この変更は、Microsoft サポートを通じて以前に発表されたのが、Office [365 での TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の使用の準備です。</span><span class="sxs-lookup"><span data-stu-id="1dbef-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="1dbef-107">お客様のデータのセキュリティは重要であり、お客様によるサービスの使用に影響を与える可能性のある変更に関する透明性に取り組み、取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="1dbef-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="1dbef-108">Microsoft [TLS 1.0 の](https://support.microsoft.com/help/3117336) 実装には既知のセキュリティの脆弱性はありませんが、FedRAMP コンプライアンス標準に引き続きコミットしています。</span><span class="sxs-lookup"><span data-stu-id="1dbef-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="1dbef-109">そのため、2020 年 1 月 15 日に、GCC High および DoD 環境の Office 365 で TLS 1.1 および 1.0 を無効にしました。</span><span class="sxs-lookup"><span data-stu-id="1dbef-109">Therefore, we disabled TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="1dbef-110">TLS 1.1 と 1.0 の依存関係を削除する方法については、次のホワイト ペーパーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dbef-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="1dbef-111">TLS 1.0 の問題の解決</span><span class="sxs-lookup"><span data-stu-id="1dbef-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="1dbef-112">代わりに TLS バージョン 1.2 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dbef-112">You must use TLS version 1.2 instead.</span></span> <span data-ttu-id="1dbef-113">詳細については、「Office [365 での TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須の使用の準備」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dbef-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="1dbef-114">SharePoint と OneDrive の場合は、TLS 1.2 をサポートするために .NET を更新して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dbef-114">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="1dbef-115">詳細については、「クライアントで [TLS 1.2 を有効にする方法」を参照してください](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。</span><span class="sxs-lookup"><span data-stu-id="1dbef-115">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="1dbef-116">詳細情報</span><span class="sxs-lookup"><span data-stu-id="1dbef-116">More information</span></span>

<span data-ttu-id="1dbef-117">2020 年 1 月 15 日から、GCC High および DoD 環境の Office 365 は TLS 1.1 および 1.0 を廃止する予定です。</span><span class="sxs-lookup"><span data-stu-id="1dbef-117">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="1dbef-118">2020 年 1 月 15 日までには、クライアント サーバーとブラウザー サーバーのすべての組み合わせで TLS バージョン 1.2 (以降のバージョン) を使用して、Office 365 サービスへの問題なくすべての接続を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dbef-118">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="1dbef-119">これには、クライアント サーバーとブラウザー サーバーの特定の組み合わせに対する更新が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1dbef-119">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="1dbef-120">2020 年 1 月 15 日まで TLS バージョン 1.2 (以降のバージョン) に更新しない場合は、Office 365 に接続しようとするときに問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="1dbef-120">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="1dbef-121">さらに、解決の一環として TLS 1.2 (以降のバージョン) に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dbef-121">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="1dbef-122">次のクライアントでは TLS 1.2 を使用できないことがわかっています。</span><span class="sxs-lookup"><span data-stu-id="1dbef-122">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="1dbef-123">Android 4.3 およびそれ以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="1dbef-123">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="1dbef-124">Firefox 5.0 およびそれ以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="1dbef-124">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="1dbef-125">windows 7 Internet Explorer 8以前のバージョンでの Internet Explorer 8-10</span><span class="sxs-lookup"><span data-stu-id="1dbef-125">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="1dbef-126">Internet Explorer 8.0 の Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="1dbef-126">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="1dbef-127">Safari 6.0.4/OS X 10.8.4 以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="1dbef-127">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="1dbef-128">クライアントを更新して、365 GCC High および DoD Office中断なくアクセスすることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1dbef-128">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="1dbef-129">Microsoft Online サービスへの接続の現在の分析では、ほとんどのサービスとエンドポイントで TLS 1.1 と 1.0 の使用はほとんど見えながちですが、TLS 1.1 および 1.0 のサポートが終了する前に、影響を受けるクライアントまたはサーバーを必要に応じて更新できるよう、この変更に関する通知を提供しています。</span><span class="sxs-lookup"><span data-stu-id="1dbef-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="1dbef-130">ハイブリッド シナリオまたは Active Directory フェデレーション サービス (AD FS) にオンプレミスのインフラストラクチャを使用している場合は、そのインフラストラクチャが TLS 1.2 (または以降のバージョン) を使用する受信接続と送信接続の両方をサポートできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dbef-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="1dbef-131">TLS 1.2 を使用できない一覧のクライアントを使用した場合に発生する可能性がある停止に加えて、TLS 1.1 と 1.0 を削除すると、次の Microsoft 製品を使用できません。</span><span class="sxs-lookup"><span data-stu-id="1dbef-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="1dbef-132">Lync 電話</span><span class="sxs-lookup"><span data-stu-id="1dbef-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="1dbef-133">関連情報</span><span class="sxs-lookup"><span data-stu-id="1dbef-133">References</span></span>

<span data-ttu-id="1dbef-134">次のサポート記事では、クライアントが TLS 1.2 を使用する場合に役立つガイダンスと参照情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="1dbef-134">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="1dbef-135">OFFICE 365 での TLS 1.2 の必須使用の準備</span><span class="sxs-lookup"><span data-stu-id="1dbef-135">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
