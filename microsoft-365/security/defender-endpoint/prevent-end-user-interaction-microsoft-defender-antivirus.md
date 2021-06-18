---
title: インターフェイスをMicrosoft Defender ウイルス対策する
description: アプリでウイルスと脅威の保護タイルをWindows セキュリティできます。
keywords: ui lockdown, headless mode, hide app, hide settings, hide interface
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007679"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="9e6c2-104">ユーザーがユーザー インターフェイスを表示または操作Microsoft Defender ウイルス対策防止する</span><span class="sxs-lookup"><span data-stu-id="9e6c2-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9e6c2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9e6c2-105">**Applies to:**</span></span>

- [<span data-ttu-id="9e6c2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9e6c2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9e6c2-107">グループ ポリシーを使用すると、エンドポイント上のユーザーにインターフェイスが表示Microsoft Defender ウイルス対策できます。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="9e6c2-108">また、スキャンの一時停止を防止することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="9e6c2-109">インターフェイスをMicrosoft Defender ウイルス対策する</span><span class="sxs-lookup"><span data-stu-id="9e6c2-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="9e6c2-110">このWindows 10バージョン 1703 では、インターフェイスを非表示にすると、Microsoft Defender ウイルス対策 通知が非表示にされ、ウイルス & の脅威保護タイルが Windows セキュリティ アプリに表示されWindows セキュリティされます。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="9e6c2-111">設定を [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-111">With the setting set to **Enabled**:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Windows セキュリティアイコンとウイルスと脅威の保護セクションがない場合":::

<span data-ttu-id="9e6c2-113">設定が [無効] または **[** 構成されていない] に設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="9e6c2-113">With the setting set to **Disabled** or not configured:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="シールド アイコンとWindows セキュリティ保護セクションを含むアプリのスクリーンショット":::

>[!NOTE]
><span data-ttu-id="9e6c2-115">インターフェイスを非表示にすることで、Microsoft Defender ウイルス対策通知がエンドポイントに表示されるのを防ぐことも可能です。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="9e6c2-116">Microsoft Defender for Endpoint 通知は引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="9e6c2-117">エンドポイントに表示 [される通知を個別に構成することもできます](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9e6c2-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="9e6c2-118">以前のバージョンの Windows 10設定では、クライアント インターフェイスWindows Defender非表示になります。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="9e6c2-119">ユーザーが開くしようとすると、「システム管理者は、このアプリへのアクセスを制限しました」という警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="1703 より前のバージョンの Windows 10でヘッドレス モードが有効になっている場合の警告メッセージ":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="9e6c2-121">グループ ポリシーを使用して Microsoft Defender AV インターフェイスをユーザーから非表示にする</span><span class="sxs-lookup"><span data-stu-id="9e6c2-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="9e6c2-122">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="9e6c2-123">グループ ポリシー管理 **エディターを使用して、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="9e6c2-124">[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="9e6c2-125">ツリーを展開して **、Windowsインターフェイス> Microsoft Defender ウイルス対策 >コンポーネントを表示します**。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="9e6c2-126">[ヘッドレス UI モードを有効にする] **設定を** ダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="9e6c2-127">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-127">Click **OK**.</span></span> 

<span data-ttu-id="9e6c2-128">ユーザー [が PC の保護を](configure-local-policy-overrides-microsoft-defender-antivirus.md) 変更する方法の詳細については、「ユーザーがポリシー設定をローカルで変更するのを防ぐ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="9e6c2-129">ユーザーによるスキャンの一時停止を防止する</span><span class="sxs-lookup"><span data-stu-id="9e6c2-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="9e6c2-130">ユーザーがスキャンを一時停止するのを防ぐと、スケジュールされたスキャンまたはオンデマンド スキャンがユーザーによって中断されないのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="9e6c2-131">この設定は、この設定ではWindows 10。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="9e6c2-132">グループ ポリシーを使用して、ユーザーによるスキャンの一時停止を防止する</span><span class="sxs-lookup"><span data-stu-id="9e6c2-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="9e6c2-133">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="9e6c2-134">グループ ポリシー管理 **エディターを使用して、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="9e6c2-135">[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="9e6c2-136">ツリーを展開して、[**スキャン] WindowsコンポーネントMicrosoft Defender ウイルス対策**  >    >  **展開します**。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="9e6c2-137">[ユーザーにスキャンの **一時停止を許可する** ] 設定をダブルクリックし、オプションを [無効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="9e6c2-138">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e6c2-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="9e6c2-139">関連記事</span><span class="sxs-lookup"><span data-stu-id="9e6c2-139">Related articles</span></span>

- [<span data-ttu-id="9e6c2-140">エンドポイントに表示される通知を構成する</span><span class="sxs-lookup"><span data-stu-id="9e6c2-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="9e6c2-141">ユーザーとのエンド ユーザー操作を構成Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="9e6c2-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="9e6c2-142">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="9e6c2-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)