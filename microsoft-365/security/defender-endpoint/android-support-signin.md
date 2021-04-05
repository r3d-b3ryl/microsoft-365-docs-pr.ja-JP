---
title: Microsoft Defender for Endpoint for Android の問題のトラブルシューティング
description: Microsoft Defender for Endpoint for Android の問題のトラブルシューティング
keywords: microsoft、Defender、atp、mde、android、クラウド、接続、コミュニケーション
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
ms.openlocfilehash: 5fabcb3156a54d4aa8a4671d7561a8deca16fe1f
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587649"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="82dee-104">Microsoft Defender for Endpoint for Android の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="82dee-104">Troubleshooting issues on Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="82dee-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="82dee-105">**Applies to:**</span></span>
- [<span data-ttu-id="82dee-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="82dee-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="82dee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82dee-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="82dee-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="82dee-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="82dee-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="82dee-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="82dee-110">デバイスのオンボード時に、アプリのインストール後にサインインの問題が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="82dee-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="82dee-111">オンボーディング中に、アプリがデバイスにインストールされた後にサインインの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82dee-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="82dee-112">この記事では、サインオンの問題に対処するためのソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="82dee-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="82dee-113">サインインに失敗しました - 予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="82dee-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="82dee-114">\**サインインに失敗しました: 予期しない\*\*\*エラーが発生した場合は、後で試してください*</span><span class="sxs-lookup"><span data-stu-id="82dee-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![サインインに失敗したエラーのイメージ 予期しないエラー](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="82dee-116">**メッセージ：**</span><span class="sxs-lookup"><span data-stu-id="82dee-116">**Message:**</span></span>

<span data-ttu-id="82dee-117">予期しないエラー、後で試す</span><span class="sxs-lookup"><span data-stu-id="82dee-117">Unexpected error, try later</span></span>

<span data-ttu-id="82dee-118">**原因:**</span><span class="sxs-lookup"><span data-stu-id="82dee-118">**Cause:**</span></span>

<span data-ttu-id="82dee-119">デバイスに古いバージョンの "Microsoft Authenticator" アプリがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="82dee-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="82dee-120">**解決方法:**</span><span class="sxs-lookup"><span data-stu-id="82dee-120">**Solution:**</span></span>

<span data-ttu-id="82dee-121">Google Play ストアから最新バージョンの [Microsoft Authenticator を](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) インストールし、もう一度やり直す</span><span class="sxs-lookup"><span data-stu-id="82dee-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="82dee-122">サインインに失敗しました - 無効なライセンス</span><span class="sxs-lookup"><span data-stu-id="82dee-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="82dee-123">**サインインに失敗しました:** *ライセンスが無効です。管理者に問い合わせてください*</span><span class="sxs-lookup"><span data-stu-id="82dee-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![サインインに失敗したイメージは、管理者に問い合わせてください](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="82dee-125">**メッセージ:** *無効なライセンス、管理者に問い合わせてください*</span><span class="sxs-lookup"><span data-stu-id="82dee-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="82dee-126">**原因:**</span><span class="sxs-lookup"><span data-stu-id="82dee-126">**Cause:**</span></span>

<span data-ttu-id="82dee-127">Microsoft 365 ライセンスが割り当てられていないか、組織に Microsoft 365 Enterprise サブスクリプションのライセンスが割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="82dee-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="82dee-128">**解決方法:**</span><span class="sxs-lookup"><span data-stu-id="82dee-128">**Solution:**</span></span>

<span data-ttu-id="82dee-129">ヘルプについては、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="82dee-129">Contact your administrator for help.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="82dee-130">一部の OEM デバイスでフィッシング ページがブロックされない</span><span class="sxs-lookup"><span data-stu-id="82dee-130">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="82dee-131">**適用対象:** 特定の OEM のみ</span><span class="sxs-lookup"><span data-stu-id="82dee-131">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="82dee-132">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="82dee-132">**Xiaomi**</span></span>

<span data-ttu-id="82dee-133">Android 用 Defender for Endpoint によって検出されるフィッシングや有害な Web の脅威は、一部の Xiaomi デバイスではブロックされません。</span><span class="sxs-lookup"><span data-stu-id="82dee-133">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="82dee-134">次の機能は、これらのデバイスでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="82dee-134">The following functionality doesn't work on these devices.</span></span>

![安全でないと報告されたサイトの画像](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="82dee-136">**原因:**</span><span class="sxs-lookup"><span data-stu-id="82dee-136">**Cause:**</span></span>

<span data-ttu-id="82dee-137">Xiaomi デバイスには、新しいアクセス許可モデルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="82dee-137">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="82dee-138">これにより、Defender for Endpoint for Android では、バックグラウンドで実行されている間にポップアップ ウィンドウが表示されなかっています。</span><span class="sxs-lookup"><span data-stu-id="82dee-138">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="82dee-139">Xiaomi デバイスのアクセス許可: "バックグラウンドで実行中にポップアップ ウィンドウを表示する"</span><span class="sxs-lookup"><span data-stu-id="82dee-139">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![ポップアップ設定のイメージ](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="82dee-141">**解決方法:**</span><span class="sxs-lookup"><span data-stu-id="82dee-141">**Solution:**</span></span>

<span data-ttu-id="82dee-142">Xiaomi デバイスで必要なアクセス許可を有効にします。</span><span class="sxs-lookup"><span data-stu-id="82dee-142">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="82dee-143">バックグラウンドで実行中にポップアップ ウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="82dee-143">Display pop-up windows while running in the background.</span></span>
