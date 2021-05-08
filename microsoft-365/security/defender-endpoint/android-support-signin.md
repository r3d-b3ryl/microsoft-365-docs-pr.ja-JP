---
title: Android 上の Microsoft Defender for Endpoint の問題のトラブルシューティング
description: Android 上の Microsoft Defender for Endpoint の問題のトラブルシューティング
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mde, android, cloud, connectivity, communication
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246358"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="79767-104">Android 上の Microsoft Defender for Endpoint の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="79767-104">Troubleshooting issues on Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="79767-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="79767-105">**Applies to:**</span></span>
- [<span data-ttu-id="79767-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="79767-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="79767-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79767-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="79767-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="79767-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="79767-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="79767-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="79767-110">デバイスのオンボード時に、アプリのインストール後にサインインの問題が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="79767-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="79767-111">オンボーディング中に、アプリがデバイスにインストールされた後にサインインの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79767-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="79767-112">この記事では、サインオンの問題に対処するためのソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="79767-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="79767-113">サインインに失敗しました - 予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="79767-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="79767-114">\**サインインに失敗しました: 予期しない\*\*\*エラーが発生した場合は、後で試してください*</span><span class="sxs-lookup"><span data-stu-id="79767-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![サインインに失敗したエラーのイメージ 予期しないエラー](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="79767-116">**メッセージ：**</span><span class="sxs-lookup"><span data-stu-id="79767-116">**Message:**</span></span>

<span data-ttu-id="79767-117">予期しないエラー、後で試す</span><span class="sxs-lookup"><span data-stu-id="79767-117">Unexpected error, try later</span></span>

<span data-ttu-id="79767-118">**原因:**</span><span class="sxs-lookup"><span data-stu-id="79767-118">**Cause:**</span></span>

<span data-ttu-id="79767-119">古いバージョンの "Microsoft Authenticator" アプリがデバイスにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="79767-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="79767-120">**解決方法:**</span><span class="sxs-lookup"><span data-stu-id="79767-120">**Solution:**</span></span>

<span data-ttu-id="79767-121">Google Play ストアから最新バージョン[とMicrosoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator)をインストールし、もう一度やり直してください</span><span class="sxs-lookup"><span data-stu-id="79767-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="79767-122">サインインに失敗しました - 無効なライセンス</span><span class="sxs-lookup"><span data-stu-id="79767-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="79767-123">**サインインに失敗しました:** *ライセンスが無効です。管理者に問い合わせてください*</span><span class="sxs-lookup"><span data-stu-id="79767-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![サインインに失敗したイメージは、管理者に問い合わせてください](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="79767-125">**メッセージ:** *無効なライセンス、管理者に問い合わせてください*</span><span class="sxs-lookup"><span data-stu-id="79767-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="79767-126">**原因:**</span><span class="sxs-lookup"><span data-stu-id="79767-126">**Cause:**</span></span>

<span data-ttu-id="79767-127">ライセンスが割りMicrosoft 365されていないか、組織にサブスクリプションのライセンスMicrosoft 365 Enterpriseです。</span><span class="sxs-lookup"><span data-stu-id="79767-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="79767-128">**解決方法:**</span><span class="sxs-lookup"><span data-stu-id="79767-128">**Solution:**</span></span>

<span data-ttu-id="79767-129">ヘルプについては、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="79767-129">Contact your administrator for help.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="79767-130">安全でないサイトを報告する</span><span class="sxs-lookup"><span data-stu-id="79767-130">Report unsafe site</span></span>

<span data-ttu-id="79767-131">フィッシング Web サイトは、お客様の個人情報または財務情報を取得する目的で信頼できる Web サイトになりすます。</span><span class="sxs-lookup"><span data-stu-id="79767-131">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="79767-132">フィッシング サイト [の可能性がある Web サイトを報告](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) する場合は、[ネットワーク保護に関するフィードバックを提供する] ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="79767-132">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="79767-133">一部の OEM デバイスでフィッシング ページがブロックされない</span><span class="sxs-lookup"><span data-stu-id="79767-133">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="79767-134">**適用対象:** 特定の OEM のみ</span><span class="sxs-lookup"><span data-stu-id="79767-134">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="79767-135">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="79767-135">**Xiaomi**</span></span>

<span data-ttu-id="79767-136">Android 用 Defender for Endpoint によって検出されるフィッシングや有害な Web の脅威は、一部の Xiaomi デバイスではブロックされません。</span><span class="sxs-lookup"><span data-stu-id="79767-136">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="79767-137">次の機能は、これらのデバイスでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="79767-137">The following functionality doesn't work on these devices.</span></span>

![安全でないと報告されたサイトの画像](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="79767-139">**原因:**</span><span class="sxs-lookup"><span data-stu-id="79767-139">**Cause:**</span></span>

<span data-ttu-id="79767-140">Xiaomi デバイスには、新しいアクセス許可モデルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="79767-140">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="79767-141">これにより、Defender for Endpoint for Android では、バックグラウンドで実行されている間にポップアップ ウィンドウが表示されなかっています。</span><span class="sxs-lookup"><span data-stu-id="79767-141">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="79767-142">Xiaomi デバイスのアクセス許可: "バックグラウンドで実行中にポップアップ ウィンドウを表示する"</span><span class="sxs-lookup"><span data-stu-id="79767-142">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![ポップアップ設定のイメージ](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="79767-144">**解決方法:**</span><span class="sxs-lookup"><span data-stu-id="79767-144">**Solution:**</span></span>

<span data-ttu-id="79767-145">Xiaomi デバイスで必要なアクセス許可を有効にします。</span><span class="sxs-lookup"><span data-stu-id="79767-145">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="79767-146">バックグラウンドで実行中にポップアップ ウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="79767-146">Display pop-up windows while running in the background.</span></span>
