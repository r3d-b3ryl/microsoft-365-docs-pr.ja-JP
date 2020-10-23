---
title: Office 365 の TLS 1.0 および1.1の 廃止
description: Office 365 の TLS 1.0 および1.1 が廃止されたことについて説明します。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: ab3685883ac08522ab9ea1ee0cf194ba263d9166
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681691"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="87efd-103">Office 365 の TLS 1.0 および1.1の 廃止</span><span class="sxs-lookup"><span data-stu-id="87efd-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>
> [!IMPORTANT]
> <span data-ttu-id="87efd-104">民間のお客様のために TLS 1.0 および1.1 の非推奨の強制を一時的に停止していますが、サプライチェーンが調整され、特定の国が開かれると、10月 2020 15 日に開始するように TLS の強制をリセットしています。</span><span class="sxs-lookup"><span data-stu-id="87efd-104">We temporarily halted deprecation enforcement of TLS 1.0 and 1.1 for commercial customers due to covid-19, but as supply chains have adjusted and certain countries open back up, we are resetting the TLS enforcement to begin Oct 15, 2020 and rollout will continue over the following weeks and months.</span></span> 

<span data-ttu-id="87efd-105">2018年10月31日の時点で、Office 365 サービスのトランスポート層セキュリティ (TLS) 1.0 および1.1 プロトコルは使用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="87efd-105">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="87efd-106">エンドユーザーへの影響は最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="87efd-106">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="87efd-107">この変更は、2年以上にわたって公表されており、最初のパブリックアナウンスは2017年12月に行われています。</span><span class="sxs-lookup"><span data-stu-id="87efd-107">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="87efd-108">この記事は、office 365 のローカルクライアントを Office 365 サービスに関連するものだけを対象としていますが、Office および Office Online Server/Office Web Apps のオンプレミスの TLS の問題にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="87efd-108">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="87efd-109">Office と TLS の概要</span><span class="sxs-lookup"><span data-stu-id="87efd-109">Office and TLS overview</span></span>

<span data-ttu-id="87efd-110">Office クライアントは、Windows web サービス (WINHTTP) に依存して、TLS プロトコル経由のトラフィックの送受信を行います。</span><span class="sxs-lookup"><span data-stu-id="87efd-110">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="87efd-111">ローカルコンピューターの web サービスが TLS 1.2 を使用できる場合、Office クライアントは TLS 1.2 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="87efd-111">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="87efd-112">Tls および SSL プロトコルはオペレーティングシステムの一部であり、Office クライアントに固有ではないため、すべての Office クライアントで TLS プロトコルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="87efd-112">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="87efd-113">Windows 8 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="87efd-113">On Windows 8 and later versions</span></span>

<span data-ttu-id="87efd-114">既定では、TLS 1.2 トラフィックを拒否するようにネットワークデバイスが構成されていない場合、TLS 1.2 および1.1 プロトコルが使用できます。</span><span class="sxs-lookup"><span data-stu-id="87efd-114">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="87efd-115">Windows 7</span><span class="sxs-lookup"><span data-stu-id="87efd-115">On Windows 7</span></span>

<span data-ttu-id="87efd-116">TLS 1.1 および1.2 プロトコルは、 [KB 3140245](https://support.microsoft.com/help/3140245) の更新プログラムがないと使用できません。</span><span class="sxs-lookup"><span data-stu-id="87efd-116">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="87efd-117">この更新プログラムはこの問題に対処し、次のレジストリサブキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="87efd-117">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="87efd-118">この更新プログラムをインストールしていない Windows 7 ユーザーは、2018年10月31日の時点で影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="87efd-118">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="87efd-119">[KB 3140245](https://support.microsoft.com/help/3140245) は、WINHTTP 設定を変更して TLS プロトコルを有効にする方法についての詳細を示しています。</span><span class="sxs-lookup"><span data-stu-id="87efd-119">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="87efd-120">詳細</span><span class="sxs-lookup"><span data-stu-id="87efd-120">More information</span></span>

<span data-ttu-id="87efd-121">KB の記事に記載されている **Defaultsecureprotocols** レジストリキーの値は、どのネットワークプロトコルを使用できるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="87efd-121">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="87efd-122">DefaultSecureProtocols の値</span><span class="sxs-lookup"><span data-stu-id="87efd-122">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="87efd-123">プロトコルの有効化</span><span class="sxs-lookup"><span data-stu-id="87efd-123">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="87efd-124">0x00000008</span><span class="sxs-lookup"><span data-stu-id="87efd-124">0x00000008</span></span>|<span data-ttu-id="87efd-125">既定で SSL 2.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="87efd-125">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="87efd-126">0x00000020</span><span class="sxs-lookup"><span data-stu-id="87efd-126">0x00000020</span></span>|<span data-ttu-id="87efd-127">既定で SSL 3.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="87efd-127">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="87efd-128">0x00000080</span><span class="sxs-lookup"><span data-stu-id="87efd-128">0x00000080</span></span>|<span data-ttu-id="87efd-129">既定で TLS 1.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="87efd-129">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="87efd-130">0x00000200</span><span class="sxs-lookup"><span data-stu-id="87efd-130">0x00000200</span></span>|<span data-ttu-id="87efd-131">既定で TLS 1.1 を有効にします</span><span class="sxs-lookup"><span data-stu-id="87efd-131">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="87efd-132">0x00000800</span><span class="sxs-lookup"><span data-stu-id="87efd-132">0x00000800</span></span>|<span data-ttu-id="87efd-133">既定で TLS 1.2 を有効にします</span><span class="sxs-lookup"><span data-stu-id="87efd-133">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="87efd-134">Office クライアントと TLS レジストリキー</span><span class="sxs-lookup"><span data-stu-id="87efd-134">Office clients and TLS registry keys</span></span>

<span data-ttu-id="87efd-135">[Office 365 で TLS 1.2 を必須で使用するための準備として、KB 4057306](https://support.microsoft.com/help/4057306)を参照することができます。</span><span class="sxs-lookup"><span data-stu-id="87efd-135">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="87efd-136">これは IT 管理者向けの一般的な記事であり、TLS 1.2 の変更に関する公式ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="87efd-136">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="87efd-137">次の表に、2018年10月31日以降の Office 365 クライアントの適切なレジストリキー値を示します。</span><span class="sxs-lookup"><span data-stu-id="87efd-137">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="87efd-138">2018年10月31日以降の Office 365 サービスの有効化プロトコル</span><span class="sxs-lookup"><span data-stu-id="87efd-138">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="87efd-139">16進値</span><span class="sxs-lookup"><span data-stu-id="87efd-139">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="87efd-140">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="87efd-140">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="87efd-141">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="87efd-141">0x00000A80</span></span>|
|<span data-ttu-id="87efd-142">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="87efd-142">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="87efd-143">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="87efd-143">0x00000A00</span></span>|
|<span data-ttu-id="87efd-144">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="87efd-144">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="87efd-145">0x00000880</span><span class="sxs-lookup"><span data-stu-id="87efd-145">0x00000880</span></span>|
|<span data-ttu-id="87efd-146">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="87efd-146">TLS 1.2</span></span>|<span data-ttu-id="87efd-147">0x00000800</span><span class="sxs-lookup"><span data-stu-id="87efd-147">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="87efd-148">SSL 2.0 および3.0 プロトコルを使用することはお勧めしません。これは、 **Defaultsecureprotocols** キーを使用して設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="87efd-148">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="87efd-149">SSL 2.0 および3.0 は、非推奨プロトコルと見なされます。</span><span class="sxs-lookup"><span data-stu-id="87efd-149">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="87efd-150">最善の方法は、SSL 2.0 および SSL 3.0 の使用を終了することですが、これを最終的に決定することは、製品のニーズに最も適した内容によって決まります。</span><span class="sxs-lookup"><span data-stu-id="87efd-150">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="87efd-151">SSL 3.0 の脆弱性の詳細については、「 [KB 3009008](https://support.microsoft.com/help/3009008)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87efd-151">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="87efd-152">既定の Windows 電卓をプログラマモードで使用して、同じ参照レジストリキーの値を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="87efd-152">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="87efd-153">詳細については、「 [KB 3140245 更新プログラム」を参照して、Windows の WinHTTP で既定のセキュリティ保護されたプロトコルとして tls 1.1 と tls 1.2 を有効](https://support.microsoft.com/help/3140245)にします。</span><span class="sxs-lookup"><span data-stu-id="87efd-153">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="87efd-154">Windows 7 更新プログラム ([KB 3140245](https://support.microsoft.com/help/3140245)) がインストールされているかどうかにかかわらず、DefaultSecureProtocols のレジストリサブキーは存在しないため、手動で追加するか、グループポリシーオブジェクト (GPO) を使用して追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87efd-154">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="87efd-155">つまり、有効または制限のあるセキュリティで保護されたプロトコルをカスタマイズする必要がない場合は、このキーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="87efd-155">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="87efd-156">Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) の更新プログラムのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="87efd-156">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
