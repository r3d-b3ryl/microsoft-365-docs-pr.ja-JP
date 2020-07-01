---
title: Office 365 の TLS 1.0 および1.1 は廃止された
description: Office 365 の TLS 1.0 および1.1 が廃止されたことについて説明します。
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 611b6970c3ecb95f4cdf046b96a5e3aa9155391d
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937345"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="10737-103">Office 365 の TLS 1.0 および1.1 は廃止された</span><span class="sxs-lookup"><span data-stu-id="10737-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>

<span data-ttu-id="10737-104">2018年10月31日の時点で、Office 365 サービスのトランスポート層セキュリティ (TLS) 1.0 および1.1 プロトコルは使用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="10737-104">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="10737-105">エンドユーザーへの影響は最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="10737-105">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="10737-106">この変更は、約2年間で公表されており、最初の公開アナウンスは2017年12月に行われています。</span><span class="sxs-lookup"><span data-stu-id="10737-106">This change was publicized for almost two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="10737-107">この記事は、office 365 のローカルクライアントを Office 365 サービスに関連するものだけを対象としていますが、Office および Office Online Server/Office Web Apps のオンプレミスの TLS の問題にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="10737-107">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="10737-108">Office と TLS の概要</span><span class="sxs-lookup"><span data-stu-id="10737-108">Office and TLS overview</span></span>

<span data-ttu-id="10737-109">Office クライアントは、Windows web サービス (WINHTTP) に依存して、TLS プロトコル経由のトラフィックの送受信を行います。</span><span class="sxs-lookup"><span data-stu-id="10737-109">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="10737-110">ローカルコンピューターの web サービスが TLS 1.2 を使用できる場合、Office クライアントは TLS 1.2 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="10737-110">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="10737-111">Tls および SSL プロトコルはオペレーティングシステムの一部であり、Office クライアントに固有ではないため、すべての Office クライアントで TLS プロトコルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="10737-111">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="10737-112">Windows 8 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="10737-112">On Windows 8 and later versions</span></span>

<span data-ttu-id="10737-113">既定では、TLS 1.2 トラフィックを拒否するようにネットワークデバイスが構成されていない場合、TLS 1.2 および1.1 プロトコルが使用できます。</span><span class="sxs-lookup"><span data-stu-id="10737-113">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="10737-114">Windows 7</span><span class="sxs-lookup"><span data-stu-id="10737-114">On Windows 7</span></span>

<span data-ttu-id="10737-115">TLS 1.1 および1.2 プロトコルは、 [KB 3140245](https://support.microsoft.com/help/3140245)の更新プログラムがないと使用できません。</span><span class="sxs-lookup"><span data-stu-id="10737-115">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="10737-116">この更新プログラムはこの問題に対処し、次のレジストリサブキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="10737-116">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="10737-117">この更新プログラムをインストールしていない Windows 7 ユーザーは、2018年10月31日の時点で影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="10737-117">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="10737-118">[KB 3140245](https://support.microsoft.com/help/3140245)は、WINHTTP 設定を変更して TLS プロトコルを有効にする方法についての詳細を示しています。</span><span class="sxs-lookup"><span data-stu-id="10737-118">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="10737-119">詳細</span><span class="sxs-lookup"><span data-stu-id="10737-119">More information</span></span>

<span data-ttu-id="10737-120">KB の記事に記載されている**Defaultsecureprotocols**レジストリキーの値は、どのネットワークプロトコルを使用できるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="10737-120">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="10737-121">DefaultSecureProtocols の値</span><span class="sxs-lookup"><span data-stu-id="10737-121">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="10737-122">プロトコルの有効化</span><span class="sxs-lookup"><span data-stu-id="10737-122">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="10737-123">0x00000008</span><span class="sxs-lookup"><span data-stu-id="10737-123">0x00000008</span></span>|<span data-ttu-id="10737-124">既定で SSL 2.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="10737-124">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="10737-125">0x00000020</span><span class="sxs-lookup"><span data-stu-id="10737-125">0x00000020</span></span>|<span data-ttu-id="10737-126">既定で SSL 3.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="10737-126">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="10737-127">0x00000080</span><span class="sxs-lookup"><span data-stu-id="10737-127">0x00000080</span></span>|<span data-ttu-id="10737-128">既定で TLS 1.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="10737-128">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="10737-129">0x00000200</span><span class="sxs-lookup"><span data-stu-id="10737-129">0x00000200</span></span>|<span data-ttu-id="10737-130">既定で TLS 1.1 を有効にします</span><span class="sxs-lookup"><span data-stu-id="10737-130">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="10737-131">0x00000800</span><span class="sxs-lookup"><span data-stu-id="10737-131">0x00000800</span></span>|<span data-ttu-id="10737-132">既定で TLS 1.2 を有効にします</span><span class="sxs-lookup"><span data-stu-id="10737-132">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="10737-133">Office クライアントと TLS レジストリキー</span><span class="sxs-lookup"><span data-stu-id="10737-133">Office clients and TLS registry keys</span></span>

<span data-ttu-id="10737-134">[Office 365 で TLS 1.2 を必須で使用するための準備として、KB 4057306](https://support.microsoft.com/help/4057306)を参照することができます。</span><span class="sxs-lookup"><span data-stu-id="10737-134">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="10737-135">これは IT 管理者向けの一般的な記事であり、TLS 1.2 の変更に関する公式ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="10737-135">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="10737-136">次の表に、2018年10月31日以降の Office 365 クライアントの適切なレジストリキー値を示します。</span><span class="sxs-lookup"><span data-stu-id="10737-136">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="10737-137">2018年10月31日以降の Office 365 サービスの有効化プロトコル</span><span class="sxs-lookup"><span data-stu-id="10737-137">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="10737-138">16進値</span><span class="sxs-lookup"><span data-stu-id="10737-138">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="10737-139">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="10737-139">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="10737-140">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="10737-140">0x00000A80</span></span>|
|<span data-ttu-id="10737-141">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="10737-141">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="10737-142">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="10737-142">0x00000A00</span></span>|
|<span data-ttu-id="10737-143">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="10737-143">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="10737-144">0x00000880</span><span class="sxs-lookup"><span data-stu-id="10737-144">0x00000880</span></span>|
|<span data-ttu-id="10737-145">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="10737-145">TLS 1.2</span></span>|<span data-ttu-id="10737-146">0x00000800</span><span class="sxs-lookup"><span data-stu-id="10737-146">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="10737-147">SSL 2.0 および3.0 プロトコルを使用することはお勧めしません。これは、 **Defaultsecureprotocols**キーを使用して設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="10737-147">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="10737-148">SSL 2.0 および3.0 は、非推奨プロトコルと見なされます。</span><span class="sxs-lookup"><span data-stu-id="10737-148">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="10737-149">最善の方法は、SSL 2.0 および SSL 3.0 の使用を終了することですが、これを最終的に決定することは、製品のニーズに最も適した内容によって決まります。</span><span class="sxs-lookup"><span data-stu-id="10737-149">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="10737-150">SSL 3.0 の脆弱性の詳細については、「 [KB 3009008](https://support.microsoft.com/help/3009008)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10737-150">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="10737-151">既定の Windows 電卓をプログラマモードで使用して、同じ参照レジストリキーの値を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="10737-151">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="10737-152">詳細については、「 [KB 3140245 更新プログラム」を参照して、Windows の WinHTTP で既定のセキュリティ保護されたプロトコルとして tls 1.1 と tls 1.2 を有効](https://support.microsoft.com/help/3140245)にします。</span><span class="sxs-lookup"><span data-stu-id="10737-152">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="10737-153">Windows 7 更新プログラム ([KB 3140245](https://support.microsoft.com/help/3140245)) がインストールされているかどうかにかかわらず、DefaultSecureProtocols のレジストリサブキーは存在しないため、手動で追加するか、グループポリシーオブジェクト (GPO) を使用して追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10737-153">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="10737-154">つまり、有効または制限のあるセキュリティで保護されたプロトコルをカスタマイズする必要がない場合は、このキーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="10737-154">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="10737-155">Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) の更新プログラムのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="10737-155">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
