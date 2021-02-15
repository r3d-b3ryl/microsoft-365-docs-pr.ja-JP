---
title: Microsoft 365 での TLS 1.0 および 1.1 の無効化
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
ms.openlocfilehash: 669ab53739bfd108bdbe9077762272e6a4901865
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233099"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="8820e-103">Microsoft 365 での TLS 1.0 および 1.1 の無効化</span><span class="sxs-lookup"><span data-stu-id="8820e-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8820e-104">商用のお客様の場合、COVID-19 による TLS 1.0 および 1.1 の無効化を一時的に停止しました。</span><span class="sxs-lookup"><span data-stu-id="8820e-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="8820e-105">サプライ チェーンが調整され、特定の国がバックアップを開始すると、2020 年 10 月 15 日に TLS 1.2 実施ロールアウトが再開されました。</span><span class="sxs-lookup"><span data-stu-id="8820e-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="8820e-106">ロールアウトは、今後数週間から数か月の間続きます。</span><span class="sxs-lookup"><span data-stu-id="8820e-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="8820e-107">2018 年 10 月 31 日の現在、トランスポート層セキュリティ (TLS) 1.0 および 1.1 プロトコルは、Microsoft 365 サービスでは廃止されました。</span><span class="sxs-lookup"><span data-stu-id="8820e-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="8820e-108">エンドユーザーに対する影響は最小限です。</span><span class="sxs-lookup"><span data-stu-id="8820e-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="8820e-109">この変更は、2017 年 12 月に最初の公開発表が行われたので、2 年以上前から公開されています。</span><span class="sxs-lookup"><span data-stu-id="8820e-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="8820e-110">この記事は、Office 365 サービスに関連する Office 365 ローカル クライアントのみを対象としますが、Office および Office Online Server/Office Web Apps のオンプレミス TLS の問題にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="8820e-111">SharePoint と OneDrive では、TLS 1.2 をサポートするために .NET を更新および構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8820e-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="8820e-112">詳細については、「クライアントで [TLS 1.2 を有効にする方法」を参照してください](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。</span><span class="sxs-lookup"><span data-stu-id="8820e-112">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="8820e-113">Office 365 と TLS の概要</span><span class="sxs-lookup"><span data-stu-id="8820e-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="8820e-114">クライアントOfficeは、WINDOWS Web サービス (WINHTTP) を使用して TLS プロトコルを通してトラフィックを送受信します。</span><span class="sxs-lookup"><span data-stu-id="8820e-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="8820e-115">ローカル Office Web サービスが TLS 1.2 を使用できる場合、クライアントは TLS 1.2 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="8820e-116">TLS Office SSL プロトコルはオペレーティング システムの一部であり、クライアントに固有ではなOfficeされます。</span><span class="sxs-lookup"><span data-stu-id="8820e-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="8820e-117">バージョンWindows 8以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="8820e-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="8820e-118">既定では、TLS 1.2 および 1.1 のプロトコルは、TLS 1.2 トラフィックを拒否するように構成されているネットワーク デバイスがない場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="8820e-119">Windows 7 の場合</span><span class="sxs-lookup"><span data-stu-id="8820e-119">On Windows 7</span></span>

<span data-ttu-id="8820e-120">TLS 1.1 および 1.2 プロトコルは [、KB 3140245](https://support.microsoft.com/help/3140245) の更新なしでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="8820e-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="8820e-121">この更新プログラムは、この問題に取り組み、次のレジストリ サブ キーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8820e-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="8820e-122">この更新プログラムを適用していない Windows 7 ユーザーは、2018 年 10 月 31 日の時点で影響を受ける。</span><span class="sxs-lookup"><span data-stu-id="8820e-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="8820e-123">[KB 3140245](https://support.microsoft.com/help/3140245) には、TLS プロトコルを有効にするため WINHTTP 設定を変更する方法に関する詳細があります。</span><span class="sxs-lookup"><span data-stu-id="8820e-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="8820e-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8820e-124">More information</span></span>

<span data-ttu-id="8820e-125">使用できるネットワーク プロトコルは、サポート技術情報の記事で説明されている **DefaultSecureProtocols** レジストリ キーの値によって決されます。</span><span class="sxs-lookup"><span data-stu-id="8820e-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="8820e-126">DefaultSecureProtocols 値</span><span class="sxs-lookup"><span data-stu-id="8820e-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="8820e-127">プロトコルの有効化</span><span class="sxs-lookup"><span data-stu-id="8820e-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="8820e-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="8820e-128">0x00000008</span></span>|<span data-ttu-id="8820e-129">既定で SSL 2.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="8820e-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="8820e-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="8820e-130">0x00000020</span></span>|<span data-ttu-id="8820e-131">既定で SSL 3.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="8820e-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="8820e-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="8820e-132">0x00000080</span></span>|<span data-ttu-id="8820e-133">既定で TLS 1.0 を有効にします</span><span class="sxs-lookup"><span data-stu-id="8820e-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="8820e-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="8820e-134">0x00000200</span></span>|<span data-ttu-id="8820e-135">既定で TLS 1.1 を有効にします</span><span class="sxs-lookup"><span data-stu-id="8820e-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="8820e-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="8820e-136">0x00000800</span></span>|<span data-ttu-id="8820e-137">既定で TLS 1.2 を有効にします</span><span class="sxs-lookup"><span data-stu-id="8820e-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="8820e-138">Officeクライアントと TLS レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="8820e-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="8820e-139">KB [4057306 OFFICE 365 での TLS 1.2](https://support.microsoft.com/help/4057306)の必須使用の準備に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8820e-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="8820e-140">これは IT 管理者向け一般的な記事であり、TLS 1.2 の変更に関する公式ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="8820e-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="8820e-141">次の表に、2018 年 10 月 31 日Office 365 クライアントの適切なレジストリ キー値を示します。</span><span class="sxs-lookup"><span data-stu-id="8820e-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="8820e-142">2018 年 10 Office 365 サービスで有効になっているプロトコル</span><span class="sxs-lookup"><span data-stu-id="8820e-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="8820e-143">16 進数の値</span><span class="sxs-lookup"><span data-stu-id="8820e-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="8820e-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="8820e-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="8820e-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="8820e-145">0x00000A80</span></span>|
|<span data-ttu-id="8820e-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="8820e-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="8820e-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="8820e-147">0x00000A00</span></span>|
|<span data-ttu-id="8820e-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="8820e-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="8820e-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="8820e-149">0x00000880</span></span>|
|<span data-ttu-id="8820e-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="8820e-150">TLS 1.2</span></span>|<span data-ttu-id="8820e-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="8820e-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="8820e-152">SSL 2.0 および 3.0 プロトコルは使用しない **(DefaultSecureProtocols** キーを使用して設定できる)。</span><span class="sxs-lookup"><span data-stu-id="8820e-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="8820e-153">SSL 2.0 および 3.0 は、古い安全でないプロトコルと見なされます。</span><span class="sxs-lookup"><span data-stu-id="8820e-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="8820e-154">ベスト プラクティスは SSL 2.0 と SSL 3.0 の使用を終了する方法ですが、これを行う決定は最終的には、製品のニーズに最も合う内容によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8820e-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="8820e-155">SSL 3.0 の脆弱性の詳細については [、KB 3009008 を参照](https://support.microsoft.com/help/3009008)してください。</span><span class="sxs-lookup"><span data-stu-id="8820e-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="8820e-156">プログラマ モードの既定の Windows 電卓を使用して、同じ参照レジストリ キー値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="8820e-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="8820e-157">詳細については、Windows の WinHTTP で TLS 1.1 および TLS 1.2 を既定のセキュリティで保護されたプロトコルとして有効にする [KB 3140245 Update](https://support.microsoft.com/help/3140245)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8820e-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="8820e-158">Windows 7 更新プログラム ([KB 3140245)](https://support.microsoft.com/help/3140245)がインストールされている場合でもインストールされていない場合でも、DefaultSecureProtocols レジストリ サブキーは存在しなく、手動で追加するか、グループ ポリシー オブジェクト (GPO) を使用して追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8820e-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="8820e-159">つまり、有効または制限されているセキュリティで保護されたプロトコルをカスタマイズする必要がない限り、このキーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8820e-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="8820e-160">必要なのは、Windows 7 SP1 ([KB 3140245)](https://support.microsoft.com/help/3140245)更新プログラムのみです。</span><span class="sxs-lookup"><span data-stu-id="8820e-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="8820e-161">TLS 1.2 をサポートするために .NET Framework を更新および構成する</span><span class="sxs-lookup"><span data-stu-id="8820e-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="8820e-162">TLS 1.0 または TLS 1.1 経由で Microsoft 365 API を呼び出すアプリケーションを更新して TLS 1.2 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8820e-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="8820e-163">.NET 4.5 の既定値は TLS 1.1 です。</span><span class="sxs-lookup"><span data-stu-id="8820e-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="8820e-164">.NET 構成を更新するには、「クライアントでトランスポート層セキュリティ [(TLS) 1.2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)を有効にする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8820e-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="8820e-165">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8820e-165">More information</span></span>

<span data-ttu-id="8820e-166">詳細については、「Office [365 での TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須の使用の準備」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8820e-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
