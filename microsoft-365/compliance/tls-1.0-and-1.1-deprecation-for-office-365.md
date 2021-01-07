---
title: Office 365 の TLS 1.0 および1.1の 廃止
description: Office 365 での TLS 1.0 および 1.1 の廃止について説明します。
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
ms.openlocfilehash: 622d783011defcf9c84061087b7d05f2a117172e
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777059"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="ce1d7-103">Office 365 の TLS 1.0 および1.1の 廃止</span><span class="sxs-lookup"><span data-stu-id="ce1d7-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>
> [!IMPORTANT]
> <span data-ttu-id="ce1d7-104">商用のお客様に対する TLS 1.0 および 1.1 の廃止の強制は、COVID-19 により一時的に停止されましたが、サプライ チェーンが調整され、一部の国が開いているので、2020 年 10 月 15 日に開始するために TLS の適用がリセットされ、ロールアウトは数週間から数か月続きます。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-104">We temporarily halted deprecation enforcement of TLS 1.0 and 1.1 for commercial customers due to COVID-19, but as supply chains have adjusted and certain countries open back up, we are resetting the TLS enforcement to begin October 15, 2020, and rollout will continue over the following weeks and months.</span></span> 

<span data-ttu-id="ce1d7-105">2018 年 10 月 31 日の現在、トランスポート層セキュリティ (TLS) 1.0 および 1.1 プロトコルは Office 365 サービスで廃止されました。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-105">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="ce1d7-106">エンドユーザーに対する影響は最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-106">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="ce1d7-107">この変更は、2017 年 12 月に最初の公開発表が行われたので、2 年以上前から公開されています。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-107">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="ce1d7-108">この記事は、Office 365 サービスに関連する Office 365 ローカル クライアントのみを対象としますが、Office および Office Online Server/Office Web Apps のオンプレミス TLS の問題にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-108">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="ce1d7-109">Office TLS の概要</span><span class="sxs-lookup"><span data-stu-id="ce1d7-109">Office and TLS overview</span></span>

<span data-ttu-id="ce1d7-110">クライアントOfficeは、WINDOWS Web サービス (WINHTTP) を使用して TLS プロトコルを通してトラフィックを送受信します。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-110">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="ce1d7-111">ローカル Office Web サービスが TLS 1.2 を使用できる場合、クライアントは TLS 1.2 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-111">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="ce1d7-112">TLS Office SSL プロトコルはオペレーティング システムの一部であり、クライアントに固有ではなOfficeです。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-112">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="ce1d7-113">バージョンWindows 8以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="ce1d7-113">On Windows 8 and later versions</span></span>

<span data-ttu-id="ce1d7-114">既定では、TLS 1.2 および 1.1 のプロトコルは、TLS 1.2 トラフィックを拒否するように構成されているネットワーク デバイスがない場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-114">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="ce1d7-115">Windows 7 の場合</span><span class="sxs-lookup"><span data-stu-id="ce1d7-115">On Windows 7</span></span>

<span data-ttu-id="ce1d7-116">TLS 1.1 および 1.2 プロトコルは [、KB 3140245](https://support.microsoft.com/help/3140245) の更新なしでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-116">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="ce1d7-117">この更新プログラムは、この問題に取り組み、次のレジストリ サブ キーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-117">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="ce1d7-118">この更新プログラムを適用していない Windows 7 ユーザーは、2018 年 10 月 31 日の時点で影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-118">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="ce1d7-119">[KB 3140245](https://support.microsoft.com/help/3140245) には、TLS プロトコルを有効にするため WINHTTP 設定を変更する方法に関する詳細があります。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-119">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="ce1d7-120">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ce1d7-120">More information</span></span>

<span data-ttu-id="ce1d7-121">使用できるネットワーク プロトコルは、サポート技術情報の記事で説明されている **DefaultSecureProtocols** レジストリ キーの値によって決されます。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-121">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="ce1d7-122">DefaultSecureProtocols 値</span><span class="sxs-lookup"><span data-stu-id="ce1d7-122">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="ce1d7-123">プロトコルの有効化</span><span class="sxs-lookup"><span data-stu-id="ce1d7-123">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="ce1d7-124">0x00000008</span><span class="sxs-lookup"><span data-stu-id="ce1d7-124">0x00000008</span></span>|<span data-ttu-id="ce1d7-125">既定で SSL 2.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="ce1d7-125">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="ce1d7-126">0x00000020</span><span class="sxs-lookup"><span data-stu-id="ce1d7-126">0x00000020</span></span>|<span data-ttu-id="ce1d7-127">既定で SSL 3.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="ce1d7-127">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="ce1d7-128">0x00000080</span><span class="sxs-lookup"><span data-stu-id="ce1d7-128">0x00000080</span></span>|<span data-ttu-id="ce1d7-129">既定で TLS 1.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="ce1d7-129">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="ce1d7-130">0x00000200</span><span class="sxs-lookup"><span data-stu-id="ce1d7-130">0x00000200</span></span>|<span data-ttu-id="ce1d7-131">既定で TLS 1.1 を有効にします</span><span class="sxs-lookup"><span data-stu-id="ce1d7-131">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="ce1d7-132">0x00000800</span><span class="sxs-lookup"><span data-stu-id="ce1d7-132">0x00000800</span></span>|<span data-ttu-id="ce1d7-133">既定で TLS 1.2 を有効にします</span><span class="sxs-lookup"><span data-stu-id="ce1d7-133">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="ce1d7-134">Officeクライアントと TLS レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="ce1d7-134">Office clients and TLS registry keys</span></span>

<span data-ttu-id="ce1d7-135">KB [4057306 OFFICE 365 での TLS 1.2](https://support.microsoft.com/help/4057306)の必須使用の準備に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-135">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="ce1d7-136">これは IT 管理者向け一般的な記事であり、TLS 1.2 の変更に関する公式ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-136">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="ce1d7-137">次の表に、2018 年 10 月 31 日Office 365 クライアントの適切なレジストリ キー値を示します。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-137">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="ce1d7-138">2018 年 10 Office 365 サービスで有効になっているプロトコル</span><span class="sxs-lookup"><span data-stu-id="ce1d7-138">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="ce1d7-139">16 進数の値</span><span class="sxs-lookup"><span data-stu-id="ce1d7-139">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="ce1d7-140">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="ce1d7-140">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="ce1d7-141">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="ce1d7-141">0x00000A80</span></span>|
|<span data-ttu-id="ce1d7-142">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="ce1d7-142">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="ce1d7-143">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="ce1d7-143">0x00000A00</span></span>|
|<span data-ttu-id="ce1d7-144">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="ce1d7-144">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="ce1d7-145">0x00000880</span><span class="sxs-lookup"><span data-stu-id="ce1d7-145">0x00000880</span></span>|
|<span data-ttu-id="ce1d7-146">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="ce1d7-146">TLS 1.2</span></span>|<span data-ttu-id="ce1d7-147">0x00000800</span><span class="sxs-lookup"><span data-stu-id="ce1d7-147">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="ce1d7-148">SSL 2.0 および 3.0 プロトコルを使用することをお勧めしません。 **これは DefaultSecureProtocols** キーを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-148">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="ce1d7-149">SSL 2.0 および 3.0 は非推奨プロトコルと見なされます。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-149">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="ce1d7-150">ベスト プラクティスは SSL 2.0 と SSL 3.0 の使用を終了する方法ですが、これを行う決定は最終的には、製品のニーズに最も合う内容によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-150">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="ce1d7-151">SSL 3.0 の脆弱性の詳細については [、KB 3009008 を参照](https://support.microsoft.com/help/3009008)してください。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-151">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="ce1d7-152">プログラマ モードの既定の Windows 電卓を使用して、同じ参照レジストリ キー値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-152">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="ce1d7-153">詳細については、Windows の WinHTTP で TLS 1.1 および TLS 1.2 を既定のセキュリティで保護されたプロトコルとして有効にする [KB 3140245 Update](https://support.microsoft.com/help/3140245)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-153">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="ce1d7-154">Windows 7 更新プログラム ([KB 3140245)](https://support.microsoft.com/help/3140245)がインストールされている場合でもインストールされていない場合でも、DefaultSecureProtocols レジストリ サブキーは存在しなく、手動で追加するか、グループ ポリシー オブジェクト (GPO) を使用して追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-154">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="ce1d7-155">つまり、有効または制限されているセキュリティで保護されたプロトコルをカスタマイズする必要がない限り、このキーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-155">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="ce1d7-156">必要なのは、Windows 7 SP1 ([KB 3140245)](https://support.microsoft.com/help/3140245)更新プログラムのみです。</span><span class="sxs-lookup"><span data-stu-id="ce1d7-156">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
