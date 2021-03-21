---
title: Microsoft 365 の TLS 1.0 と 1.1 を無効にする
description: Microsoft 365 の TLS 1.0 および 1.1 の廃止と無効化について説明します。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 3d44e178d351942b4a178ddc1954ddd839665639
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919303"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="d40c1-103">Microsoft 365 の TLS 1.0 と 1.1 を無効にする</span><span class="sxs-lookup"><span data-stu-id="d40c1-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d40c1-104">COVID-19 により、商用顧客向け TLS 1.0 および 1.1 の無効化が一時的に停止されました。</span><span class="sxs-lookup"><span data-stu-id="d40c1-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="d40c1-105">サプライ チェーンが調整され、一部の国がバックアップを開始すると、2020 年 10 月 15 日に TLS 1.2 実施ロールアウトが再開されました。</span><span class="sxs-lookup"><span data-stu-id="d40c1-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="d40c1-106">ロールアウトは、次の数週間と数か月の間続きます。</span><span class="sxs-lookup"><span data-stu-id="d40c1-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="d40c1-107">2018 年 10 月 31 日現在、トランスポート層セキュリティ (TLS) 1.0 および 1.1 プロトコルは、Microsoft 365 サービスでは非推奨です。</span><span class="sxs-lookup"><span data-stu-id="d40c1-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="d40c1-108">エンド ユーザーの効果は最小限です。</span><span class="sxs-lookup"><span data-stu-id="d40c1-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="d40c1-109">この変更は 2 年以上にわたり公開され、2017 年 12 月に最初の公開発表が行われた。</span><span class="sxs-lookup"><span data-stu-id="d40c1-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="d40c1-110">この記事は、Office 365 サービスに関連する Office 365 ローカル クライアントのみを対象としますが、Office および Office Online Server/Office Web Apps のオンプレミス TLS の問題にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="d40c1-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="d40c1-111">SharePoint と OneDrive の場合は、TLS 1.2 をサポートするために .NET を更新して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d40c1-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="d40c1-112">詳細については、「クライアントで [TLS 1.2 を有効にする方法」を参照してください](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。</span><span class="sxs-lookup"><span data-stu-id="d40c1-112">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="d40c1-113">Office 365 および TLS の概要</span><span class="sxs-lookup"><span data-stu-id="d40c1-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="d40c1-114">クライアントOfficeは、TLS プロトコルを使用してトラフィックを送受信するために Windows Web サービス (WINHTTP) に依存しています。</span><span class="sxs-lookup"><span data-stu-id="d40c1-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="d40c1-115">ローカル Officeの Web サービスで TLS 1.2 を使用できる場合、クライアントは TLS 1.2 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d40c1-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="d40c1-116">TLS Office SSL プロトコルはオペレーティング システムの一部であり、クライアントに固有ではなOfficeできます。</span><span class="sxs-lookup"><span data-stu-id="d40c1-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="d40c1-117">バージョンWindows 8以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="d40c1-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="d40c1-118">既定では、TLS 1.2 および 1.1 プロトコルは、TLS 1.2 トラフィックを拒否するようにネットワーク デバイスが構成されていない場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d40c1-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="d40c1-119">Windows 7 で</span><span class="sxs-lookup"><span data-stu-id="d40c1-119">On Windows 7</span></span>

<span data-ttu-id="d40c1-120">TLS 1.1 および 1.2 プロトコルは [、KB 3140245](https://support.microsoft.com/help/3140245) 更新プログラムなしでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d40c1-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="d40c1-121">この更新プログラムは、この問題に取り組み、次のレジストリ サブキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="d40c1-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="d40c1-122">この更新プログラムを使用していない Windows 7 ユーザーは、2018 年 10 月 31 日の時点で影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="d40c1-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="d40c1-123">[KB 3140245 には](https://support.microsoft.com/help/3140245) 、WINHTTP 設定を変更して TLS プロトコルを有効にする方法に関する詳細があります。</span><span class="sxs-lookup"><span data-stu-id="d40c1-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="d40c1-124">詳細</span><span class="sxs-lookup"><span data-stu-id="d40c1-124">More information</span></span>

<span data-ttu-id="d40c1-125">KB の記事で説明 **されている DefaultSecureProtocols** レジストリ キーの値は、使用できるネットワーク プロトコルを決定します。</span><span class="sxs-lookup"><span data-stu-id="d40c1-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="d40c1-126">DefaultSecureProtocols 値</span><span class="sxs-lookup"><span data-stu-id="d40c1-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="d40c1-127">プロトコルが有効</span><span class="sxs-lookup"><span data-stu-id="d40c1-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="d40c1-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="d40c1-128">0x00000008</span></span>|<span data-ttu-id="d40c1-129">既定で SSL 2.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="d40c1-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="d40c1-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="d40c1-130">0x00000020</span></span>|<span data-ttu-id="d40c1-131">既定で SSL 3.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="d40c1-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="d40c1-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="d40c1-132">0x00000080</span></span>|<span data-ttu-id="d40c1-133">既定で TLS 1.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="d40c1-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="d40c1-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="d40c1-134">0x00000200</span></span>|<span data-ttu-id="d40c1-135">既定で TLS 1.1 を有効にします</span><span class="sxs-lookup"><span data-stu-id="d40c1-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="d40c1-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="d40c1-136">0x00000800</span></span>|<span data-ttu-id="d40c1-137">既定で TLS 1.2 を有効にします</span><span class="sxs-lookup"><span data-stu-id="d40c1-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="d40c1-138">Officeおよび TLS レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="d40c1-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="d40c1-139">「KB [4057306 TLS 1.2](https://support.microsoft.com/help/4057306)の必須使用の準備」を参照Office 365.</span><span class="sxs-lookup"><span data-stu-id="d40c1-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="d40c1-140">これは、IT 管理者向け一般的な記事であり、TLS 1.2 の変更に関する公式ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="d40c1-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="d40c1-141">次の表は、2018 年 10 月 31 日以降Office 365 クライアントの適切なレジストリ キー値を示しています。</span><span class="sxs-lookup"><span data-stu-id="d40c1-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="d40c1-142">2018 年 10 月 31 日Office 365 サービスの有効なプロトコル</span><span class="sxs-lookup"><span data-stu-id="d40c1-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="d40c1-143">16 進値</span><span class="sxs-lookup"><span data-stu-id="d40c1-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="d40c1-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="d40c1-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="d40c1-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="d40c1-145">0x00000A80</span></span>|
|<span data-ttu-id="d40c1-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="d40c1-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="d40c1-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="d40c1-147">0x00000A00</span></span>|
|<span data-ttu-id="d40c1-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="d40c1-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="d40c1-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="d40c1-149">0x00000880</span></span>|
|<span data-ttu-id="d40c1-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="d40c1-150">TLS 1.2</span></span>|<span data-ttu-id="d40c1-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="d40c1-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="d40c1-152">**DEFAULTSecureProtocols** キーを使用して設定できる SSL 2.0 および 3.0 プロトコルは使用しない。</span><span class="sxs-lookup"><span data-stu-id="d40c1-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="d40c1-153">SSL 2.0 および 3.0 は、古い安全でないプロトコルと見なされます。</span><span class="sxs-lookup"><span data-stu-id="d40c1-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="d40c1-154">ベスト プラクティスは、SSL 2.0 と SSL 3.0 の使用を終了する方法ですが、最終的には、製品のニーズに最も合った内容に依存します。</span><span class="sxs-lookup"><span data-stu-id="d40c1-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="d40c1-155">SSL 3.0 の脆弱性の詳細については [、KB 3009008 を参照してください](https://support.microsoft.com/help/3009008)。</span><span class="sxs-lookup"><span data-stu-id="d40c1-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="d40c1-156">プログラマ モードで既定の Windows Calculator を使用して、同じ参照レジストリ キー値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="d40c1-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="d40c1-157">詳細については [、「KB 3140245 Update」を参照して、Windows の WinHTTP で TLS 1.1 および TLS 1.2](https://support.microsoft.com/help/3140245)を既定のセキュリティで保護されたプロトコルとして有効にします。</span><span class="sxs-lookup"><span data-stu-id="d40c1-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="d40c1-158">Windows 7 更新プログラム[(KB 3140245)](https://support.microsoft.com/help/3140245)がインストールされている場合とインストールされていない場合は、DefaultSecureProtocols レジストリ サブキーは存在し、手動またはグループ ポリシー オブジェクト (GPO) を使用して追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d40c1-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="d40c1-159">つまり、有効または制限されているセキュリティで保護されたプロトコルをカスタマイズする必要がない限り、このキーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d40c1-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="d40c1-160">必要なのは、Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) 更新プログラムのみです。</span><span class="sxs-lookup"><span data-stu-id="d40c1-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="d40c1-161">TLS 1.2 をサポート.NET Frameworkを更新して構成する</span><span class="sxs-lookup"><span data-stu-id="d40c1-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="d40c1-162">TLS 1.0 または TLS 1.1 を使用して Microsoft 365 API を呼び出すアプリケーションを更新して、TLS 1.2 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d40c1-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="d40c1-163">.NET 4.5 の既定値は TLS 1.1 です。</span><span class="sxs-lookup"><span data-stu-id="d40c1-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="d40c1-164">.NET 構成を更新するには、「クライアントでトランスポート層セキュリティ [(TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)を有効にする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d40c1-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="d40c1-165">詳細</span><span class="sxs-lookup"><span data-stu-id="d40c1-165">More information</span></span>

<span data-ttu-id="d40c1-166">詳細については [、「365 の TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須使用の準備」を参照Officeしてください。</span><span class="sxs-lookup"><span data-stu-id="d40c1-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>