---
title: 役割ベースのアクセス制御の役割を作成および管理する
description: 役割を作成し、役割に割り当てられたアクセス許可を Microsoft Defender セキュリティ センターの役割ベースのアクセス制御実装の一部として定義する
keywords: ユーザー の役割、役割、アクセスの rbac
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065948"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a><span data-ttu-id="47bfa-104">役割ベースのアクセス制御の役割を作成および管理する</span><span class="sxs-lookup"><span data-stu-id="47bfa-104">Create and manage roles for role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="47bfa-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="47bfa-105">**Applies to:**</span></span>
- [<span data-ttu-id="47bfa-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="47bfa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="47bfa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47bfa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="47bfa-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="47bfa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="47bfa-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="47bfa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a><span data-ttu-id="47bfa-110">役割を作成し、役割を Azure Active Directory グループに割り当てる</span><span class="sxs-lookup"><span data-stu-id="47bfa-110">Create roles and assign the role to an Azure Active Directory group</span></span>

<span data-ttu-id="47bfa-111">次の手順では、Microsoft Defender セキュリティ センターで役割を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47bfa-111">The following steps guide you on how to create roles in Microsoft Defender Security Center.</span></span> <span data-ttu-id="47bfa-112">Azure Active Directory ユーザー グループが既に作成済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bfa-112">It assumes that you have already created Azure Active Directory user groups.</span></span>

1. <span data-ttu-id="47bfa-113">セキュリティ管理者または [グローバル管理者の役割が](https://securitycenter.windows.com/) 割り当てられているアカウントを使用して、Microsoft Defender セキュリティ センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="47bfa-113">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with a Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="47bfa-114">ナビゲーション ウィンドウで、[役割] **の [設定>選択します**。</span><span class="sxs-lookup"><span data-stu-id="47bfa-114">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="47bfa-115">[アイテム **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="47bfa-115">Select **Add item**.</span></span>

4. <span data-ttu-id="47bfa-116">役割に割り当てる役割名、説明、およびアクセス許可を入力します。</span><span class="sxs-lookup"><span data-stu-id="47bfa-116">Enter the role name, description, and permissions you'd like to assign to the role.</span></span>

5. <span data-ttu-id="47bfa-117">[ **次へ]** を選択して、役割を Azure セキュリティ AD割り当てる。</span><span class="sxs-lookup"><span data-stu-id="47bfa-117">Select **Next** to assign the role to an Azure AD Security group.</span></span>

6. <span data-ttu-id="47bfa-118">このロールに追加する Azure ADグループをフィルターを使用して選択します。</span><span class="sxs-lookup"><span data-stu-id="47bfa-118">Use the filter to select the Azure AD group that you'd like to add to this role to.</span></span>

7. <span data-ttu-id="47bfa-119">**保存して閉じます**。</span><span class="sxs-lookup"><span data-stu-id="47bfa-119">**Save and close**.</span></span>

8. <span data-ttu-id="47bfa-120">構成設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="47bfa-120">Apply the configuration settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47bfa-121">役割を作成したら、デバイス グループを作成し、作成した役割に割り当て、デバイス グループにアクセス権を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47bfa-121">After creating roles, you'll need to create a device group and provide access to the device group by assigning it to a role that you just created.</span></span>

### <a name="permission-options"></a><span data-ttu-id="47bfa-122">アクセス許可オプション</span><span class="sxs-lookup"><span data-stu-id="47bfa-122">Permission options</span></span>

- <span data-ttu-id="47bfa-123">**データの表示**</span><span class="sxs-lookup"><span data-stu-id="47bfa-123">**View data**</span></span>
    - <span data-ttu-id="47bfa-124">**セキュリティ操作** - ポータルですべてのセキュリティ操作データを表示する</span><span class="sxs-lookup"><span data-stu-id="47bfa-124">**Security operations** - View all security operations data in the portal</span></span>
    - <span data-ttu-id="47bfa-125">**脅威と脆弱性の管理** - ポータルで脅威と脆弱性の管理データを表示する</span><span class="sxs-lookup"><span data-stu-id="47bfa-125">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

- <span data-ttu-id="47bfa-126">**アクティブな修復アクション**</span><span class="sxs-lookup"><span data-stu-id="47bfa-126">**Active remediation actions**</span></span>
    - <span data-ttu-id="47bfa-127">**セキュリティ操作** - 応答アクションの実行、保留中の修復アクションの承認または却下、自動化とインジケーターの許可/ブロックリストの管理</span><span class="sxs-lookup"><span data-stu-id="47bfa-127">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
    - <span data-ttu-id="47bfa-128">**脅威と脆弱性の管理 - 例外処理** - 新しい例外を作成し、アクティブな例外を管理する</span><span class="sxs-lookup"><span data-stu-id="47bfa-128">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
    - <span data-ttu-id="47bfa-129">**脅威と脆弱性の管理 - 修復処理** - 新しい修復要求の送信、チケットの作成、既存の修復アクティビティの管理</span><span class="sxs-lookup"><span data-stu-id="47bfa-129">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

- <span data-ttu-id="47bfa-130">**アラートの調査** - アラートの管理、自動調査の開始、スキャンの実行、調査パッケージの収集、デバイス タグの管理、ポータブル実行可能ファイル (PE) ファイルのダウンロードのみ</span><span class="sxs-lookup"><span data-stu-id="47bfa-130">**Alerts investigation** - Manage alerts, initiate automated investigations, run scans, collect investigation packages, manage device tags, and download only portable executable (PE) files</span></span> 

- <span data-ttu-id="47bfa-131">**ポータル システム設定の管理** - ストレージ設定、SIEM、脅威の Intel API 設定の構成 (グローバルに適用)、詳細設定、自動ファイルアップロード、役割、デバイス グループ</span><span class="sxs-lookup"><span data-stu-id="47bfa-131">**Manage portal system settings** - Configure storage settings, SIEM and threat intel API settings (applies globally), advanced settings, automated file uploads, roles and device groups</span></span>

    > [!NOTE]
    > <span data-ttu-id="47bfa-132">この設定は、Microsoft Defender for Endpoint 管理者 (既定) の役割でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="47bfa-132">This setting is only available in the Microsoft Defender for Endpoint administrator (default) role.</span></span>

- <span data-ttu-id="47bfa-133">**セキュリティ センターでセキュリティ設定** を管理する - アラート抑制設定の構成、オートメーション用のフォルダー除外の管理、オンボードデバイスとオフボード デバイスの管理、電子メール通知の管理、評価ラボの管理</span><span class="sxs-lookup"><span data-stu-id="47bfa-133">**Manage security settings in Security Center** - Configure alert suppression settings, manage folder exclusions for automation, onboard and offboard devices, and manage email notifications, manage evaluation lab</span></span>

- <span data-ttu-id="47bfa-134">**ライブ応答機能**</span><span class="sxs-lookup"><span data-stu-id="47bfa-134">**Live response capabilities**</span></span>
    - <span data-ttu-id="47bfa-135">**基本的な** コマンド:</span><span class="sxs-lookup"><span data-stu-id="47bfa-135">**Basic** commands:</span></span>
        - <span data-ttu-id="47bfa-136">ライブ応答セッションを開始する</span><span class="sxs-lookup"><span data-stu-id="47bfa-136">Start a live response session</span></span>
        - <span data-ttu-id="47bfa-137">リモート デバイスで読み取り専用のライブ応答コマンドを実行する (ファイルのコピーと実行を除く)</span><span class="sxs-lookup"><span data-stu-id="47bfa-137">Perform read only live response commands on remote device (excluding file copy and execution</span></span>
    - <span data-ttu-id="47bfa-138">**高度な** コマンド:</span><span class="sxs-lookup"><span data-stu-id="47bfa-138">**Advanced** commands:</span></span>
        - <span data-ttu-id="47bfa-139">ライブ応答を介してリモート デバイスからファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="47bfa-139">Download a file from the remote device via live response</span></span>
        - <span data-ttu-id="47bfa-140">ファイル ページから PE ファイルと PE 以外のファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="47bfa-140">Download PE and non-PE files from the file page</span></span>
        - <span data-ttu-id="47bfa-141">リモート デバイスにファイルをアップロードする</span><span class="sxs-lookup"><span data-stu-id="47bfa-141">Upload a file to the remote device</span></span>
        - <span data-ttu-id="47bfa-142">ファイル ライブラリからスクリプトを表示する</span><span class="sxs-lookup"><span data-stu-id="47bfa-142">View a script from the files library</span></span>
        - <span data-ttu-id="47bfa-143">ファイル ライブラリからリモート デバイスでスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="47bfa-143">Execute a script on the remote device from the files library</span></span>

<span data-ttu-id="47bfa-144">使用可能なコマンドの詳細については、「Live 応答を使用して [デバイスを調査する」を参照してください](live-response.md)。</span><span class="sxs-lookup"><span data-stu-id="47bfa-144">For more information on the available commands, see [Investigate devices using Live response](live-response.md).</span></span>
  
## <a name="edit-roles"></a><span data-ttu-id="47bfa-145">ロールの編集</span><span class="sxs-lookup"><span data-stu-id="47bfa-145">Edit roles</span></span>

1. <span data-ttu-id="47bfa-146">セキュリティ管理者または [グローバル管理者の役割が](https://securitycenter.windows.com/) 割り当てられているアカウントを使用して、Microsoft Defender セキュリティ センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="47bfa-146">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="47bfa-147">ナビゲーション ウィンドウで、[役割] **の [設定>選択します**。</span><span class="sxs-lookup"><span data-stu-id="47bfa-147">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="47bfa-148">編集する役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="47bfa-148">Select the role you'd like to edit.</span></span>

4. <span data-ttu-id="47bfa-149">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47bfa-149">Click **Edit**.</span></span>

5. <span data-ttu-id="47bfa-150">役割に割り当てられている詳細またはグループを変更します。</span><span class="sxs-lookup"><span data-stu-id="47bfa-150">Modify the details or the groups that are assigned to the role.</span></span> 

6. <span data-ttu-id="47bfa-151">[保存 **して閉じる] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="47bfa-151">Click **Save and close**.</span></span>

## <a name="delete-roles"></a><span data-ttu-id="47bfa-152">役割の削除</span><span class="sxs-lookup"><span data-stu-id="47bfa-152">Delete roles</span></span>

1. <span data-ttu-id="47bfa-153">セキュリティ管理者または [グローバル管理者の役割が](https://securitycenter.windows.com/) 割り当てられているアカウントを使用して、Microsoft Defender セキュリティ センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="47bfa-153">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="47bfa-154">ナビゲーション ウィンドウで、[役割] **の [設定>選択します**。</span><span class="sxs-lookup"><span data-stu-id="47bfa-154">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="47bfa-155">削除する役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="47bfa-155">Select the role you'd like to delete.</span></span>

4. <span data-ttu-id="47bfa-156">ドロップダウン ボタンをクリックし、[役割の削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="47bfa-156">Click the drop-down button and select **Delete role**.</span></span>

## <a name="related-topic"></a><span data-ttu-id="47bfa-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="47bfa-157">Related topic</span></span>

- [<span data-ttu-id="47bfa-158">ポータルにアクセスするためのユーザーの基本的なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="47bfa-158">User basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="47bfa-159">デバイス グループの作成と管理</span><span class="sxs-lookup"><span data-stu-id="47bfa-159">Create and manage device groups</span></span>](machine-groups.md)