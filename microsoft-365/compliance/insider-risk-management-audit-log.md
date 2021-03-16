---
title: Insider リスク管理監査ログ
description: Microsoft 365 のインサイダー リスク管理監査ログについて説明します。
keywords: Microsoft 365、Insider リスク管理、リスク管理、コンプライアンス
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: bda9633ab37fd21fd66b3a8a53d4dd522e48ced1
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2021
ms.locfileid: "50820280"
---
# <a name="insider-risk-management-audit-log"></a><span data-ttu-id="f218f-104">Insider リスク管理監査ログ</span><span class="sxs-lookup"><span data-stu-id="f218f-104">Insider risk management audit log</span></span>

<span data-ttu-id="f218f-105">インサイダー リスク管理監査ログを使用すると、インサイダー リスク管理機能で実行されたアクションについて情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="f218f-105">The insider risk management audit log enables you to stay informed on the actions that were taken on insider risk management features.</span></span> <span data-ttu-id="f218f-106">このログを使用すると、1 つ以上のインサイダー リスク管理役割グループに割り当てられたユーザーが実行したアクションを個別に確認できます。</span><span class="sxs-lookup"><span data-stu-id="f218f-106">This log allows independent review of the actions taken by users assigned to one or more insider risk management role groups.</span></span> <span data-ttu-id="f218f-107">インサイダー リスク管理監査ログは組織で自動的に有効になり、無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f218f-107">The insider risk management audit log is automatically enabled in your organization and cannot be disabled.</span></span>

![Insider リスク管理監査ログ](../media/insider-risk-audit-log.png)

<span data-ttu-id="f218f-109">監視対象のアクティビティが発生すると、監査ログは自動的に直ちに更新され、ログはアクティビティに関する情報を 180 日間 (約 6 か月間) 保持します。</span><span class="sxs-lookup"><span data-stu-id="f218f-109">The audit log is automatically and immediately updated whenever monitored activities occur and the log retains information about the activity for 180 days (about six months).</span></span> <span data-ttu-id="f218f-110">180 日後、アクティビティのデータはログから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="f218f-110">After 180 days, the data for the activity is permanently deleted from the log.</span></span>

<span data-ttu-id="f218f-111">アクティビティ監視に含まれる領域は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f218f-111">Areas included in activity monitoring include:</span></span>

- <span data-ttu-id="f218f-112">Policies</span><span class="sxs-lookup"><span data-stu-id="f218f-112">Policies</span></span>
- <span data-ttu-id="f218f-113">ケース</span><span class="sxs-lookup"><span data-stu-id="f218f-113">Cases</span></span>
- <span data-ttu-id="f218f-114">アラート</span><span class="sxs-lookup"><span data-stu-id="f218f-114">Alerts</span></span>
- <span data-ttu-id="f218f-115">Settings</span><span class="sxs-lookup"><span data-stu-id="f218f-115">Settings</span></span>
- <span data-ttu-id="f218f-116">ユーザー</span><span class="sxs-lookup"><span data-stu-id="f218f-116">Users</span></span>
- <span data-ttu-id="f218f-117">通知テンプレート</span><span class="sxs-lookup"><span data-stu-id="f218f-117">Notice templates</span></span>

<span data-ttu-id="f218f-118">監査ログからデータを表示およびエクスポートするには、ユーザーを Insider リスク管理役割グループまたは *Insider* リスク管理 *監査* 人役割グループに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f218f-118">To view and export data from the audit log, users must be assigned to the *Insider Risk Management* or *Insider Risk Management Auditors* role groups.</span></span> <span data-ttu-id="f218f-119">インサイダー リスク管理役割グループの詳細については、「インサイダー リスク管理の概要 [手順 1: アクセス許可の有効化」を参照してください](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)。</span><span class="sxs-lookup"><span data-stu-id="f218f-119">To learn more about insider risk management role groups, see [Getting started with insider risk management Step 1: Enabling permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management).</span></span>

>[!NOTE]
><span data-ttu-id="f218f-120">内部リスク管理監査ログは、Microsoft 365 監査ログに関連付けられるので、独立した監査システムであり、個別のアクティビティに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="f218f-120">The insider risk management audit log isn't associated with the Microsoft 365 audit log, they are independent auditing systems and capture information on separate activities.</span></span> <span data-ttu-id="f218f-121">Microsoft 365 監査を無効にしても、インサイダー リスク管理内でのアクティビティ監査には影響はありません。</span><span class="sxs-lookup"><span data-stu-id="f218f-121">Disabling Microsoft 365 auditing doesn't impact activity auditing within insider risk management.</span></span>

## <a name="view-activity-in-the-insider-risk-audit-log"></a><span data-ttu-id="f218f-122">インサイダー リスク監査ログのアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="f218f-122">View activity in the insider risk audit log</span></span>

<span data-ttu-id="f218f-123">インサイダー リスク管理で監視されている機能アクティビティを表示するには、インサイダー リスク管理タブの右の領域にある **[Insider** リスク監査ログ] リンクに移動して選択します。既定では、インサイダー リスク管理アクティビティの次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f218f-123">To view feature activity monitored for insider risk management, navigate to, and select the **Insider risk audit log** link in the top-right area of any insider risk management tab. By default, you'll see the following information displayed for insider risk management activities:</span></span>

- <span data-ttu-id="f218f-124">**アクティビティ:** ユーザーがインサイダー リスク管理ソリューション内で行ったアクティビティの説明。</span><span class="sxs-lookup"><span data-stu-id="f218f-124">**Activity:** A description of the activity taken within the insider risk management solution by a user.</span></span>
- <span data-ttu-id="f218f-125">**カテゴリ:** アクティビティが実行された領域またはアイテム。</span><span class="sxs-lookup"><span data-stu-id="f218f-125">**Category:** The area or item where the activity was performed.</span></span> <span data-ttu-id="f218f-126">たとえば、ポリシー変更 *アクティビティが実行* された場合は、ポリシーがカテゴリとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="f218f-126">For example, you'll see *Policies* as the category when policy change activities were performed.</span></span>
- <span data-ttu-id="f218f-127">**次の操作で実行されるアクティビティ。** アクティビティを実行したユーザーのユーザー名。</span><span class="sxs-lookup"><span data-stu-id="f218f-127">**Activity performed by:** The user name of the user that performed the activity.</span></span>
- <span data-ttu-id="f218f-128">**日付:** アクティビティが実行された日時。</span><span class="sxs-lookup"><span data-stu-id="f218f-128">**Date:** The date and time the activity was performed.</span></span> <span data-ttu-id="f218f-129">日付と時刻は、組織のローカルの日付と時刻です。</span><span class="sxs-lookup"><span data-stu-id="f218f-129">The date and time are the local date and time for your organization.</span></span>

<span data-ttu-id="f218f-130">ログに記録されたアクティビティの詳細については、アクティビティを選択してアクティビティの詳細ウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="f218f-130">For more information about a logged activity, select the activity to display the activity details pane.</span></span> <span data-ttu-id="f218f-131">このウィンドウには、アクティビティに関する追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f218f-131">This pane includes additional information about the activity.</span></span>

## <a name="columns-and-filtering"></a><span data-ttu-id="f218f-132">列とフィルター</span><span class="sxs-lookup"><span data-stu-id="f218f-132">Columns and filtering</span></span>

<span data-ttu-id="f218f-133">監査者がログに記録されたアクティビティを簡単に確認するために、Insider リスク監査ログでフィルター **処理がサポートされています**。</span><span class="sxs-lookup"><span data-stu-id="f218f-133">To make it easier for auditors to review logged activity, filtering is supported in the **Insider risk audit log**.</span></span> <span data-ttu-id="f218f-134">基本的なフィルター処理では、キュー列をビューに追加して、ファイルとメッセージに異なるピボットを提供できます。</span><span class="sxs-lookup"><span data-stu-id="f218f-134">For basic filtering, queue columns are available to add to the view to provide different pivots on the files and messages.</span></span> <span data-ttu-id="f218f-135">アクティビティは、フィールドによって実行 **されるカテゴリ、日付範囲、\*\*\*\*およびアクティビティでフィルター処理** できます。</span><span class="sxs-lookup"><span data-stu-id="f218f-135">You can filter activities by the **Category, Date range,** and **Activity performed by** fields.</span></span>

<span data-ttu-id="f218f-136">アクティビティ キューの列見出しを追加または削除するには、[列のカスタマイズ] コントロールを使用して列オプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="f218f-136">To add or remove column headings for the activity queue, use the **Customize columns** control and select from the column options.</span></span> <span data-ttu-id="f218f-137">これらの列は、Insider リスク監査ログでサポートされる一般的な条件にマップされ、この記事の後半に記載されています。</span><span class="sxs-lookup"><span data-stu-id="f218f-137">These columns map to common conditions supported in the **Insider risk audit log** and are listed later in this article.</span></span>

## <a name="audit-log-export"></a><span data-ttu-id="f218f-138">監査ログのエクスポート</span><span class="sxs-lookup"><span data-stu-id="f218f-138">Audit log export</span></span>

<span data-ttu-id="f218f-139">Insider Risk *Management* または Insider Risk *Management Auditors* 役割グループに割り当てられたユーザーは、[Insider リスク監査ログ] ページの[エクスポート]を選択して、監査ログ内のすべてのアクティビティを .csv (コンマ区切り値) ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="f218f-139">Users assigned to the *Insider Risk Management* or *Insider Risk Management Auditors* role groups can export all activity in the audit log to a .csv (comma-separated values) file by selecting **Export** on the **Insider risk audit log** page.</span></span> <span data-ttu-id="f218f-140">アクティビティによっては、アクティビティの一部のフィールドがアクティビティに適用できない場合があります。これらのフィールドはエクスポートされたファイルに空白として表示されます。</span><span class="sxs-lookup"><span data-stu-id="f218f-140">Depending on the activity, some fields for an activity may not be applicable to the activity and these fields will appear as blank in the exported file.</span></span>

<span data-ttu-id="f218f-141">ファイルには、次のフィールドのアクティビティ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f218f-141">The file contains activity information for the following fields:</span></span>

- <span data-ttu-id="f218f-142">**次の操作で実行されるアクティビティ。** アイテム値を変更するユーザーのユーザー名。</span><span class="sxs-lookup"><span data-stu-id="f218f-142">**Activity performed by:** The user name of the user modifying an item value.</span></span> <span data-ttu-id="f218f-143">ここに記載されているユーザーは、Insider Risk Management 、 [](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management)Insider Risk *Management* Admins 、 Insider Risk Management *Analysts*、 Insider Risk Management *Investigators* の 1 つ以上の役割インサイダー リスク管理役割グループに割り当てされました。 </span><span class="sxs-lookup"><span data-stu-id="f218f-143">Users listed here were assigned to one or more of the following role [insider risk management role groups](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management): *Insider Risk Management*, *Insider Risk Management Admins*, *Insider Risk Management Analysts*, *Insider Risk Management Investigators*.</span></span> <span data-ttu-id="f218f-144">各役割グループには、インサイダー リスク機能を管理するための異なるアクセス許可レベルがあります。</span><span class="sxs-lookup"><span data-stu-id="f218f-144">Each role group has different permission levels for managing insider risk features.</span></span>
- <span data-ttu-id="f218f-145">**アクティビティ:** アイテムに対して行ったアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="f218f-145">**Activity:** The activity taken on an item.</span></span> <span data-ttu-id="f218f-146">値は *表示、削除、追加、* 編集済みポリシー、ケース、ユーザー、アラート、および設定 *です。*</span><span class="sxs-lookup"><span data-stu-id="f218f-146">Values are *Viewed, Deleted, Added, Edited policy, Case, User, Alert,* and *Settings.*</span></span>
- <span data-ttu-id="f218f-147">**追加:** ユーザー、ファイルの種類、ドメインなど、アクティビティ中に追加されたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f218f-147">**Added**: Objects that were added during the activity, such as users, file types, or domains.</span></span>
- <span data-ttu-id="f218f-148">**アラートボリューム**: Insider リスク管理設定で定義されたアラート ボリュームのレベル。</span><span class="sxs-lookup"><span data-stu-id="f218f-148">**Alert volume**: The level of alert volume defined in insider risk management settings.</span></span>
- <span data-ttu-id="f218f-149">**Amount**: ポリシーに対して現在選択されているカスタム インジケーターの量。</span><span class="sxs-lookup"><span data-stu-id="f218f-149">**Amount**: The currently selected custom indicator amounts for a policy.</span></span>
- <span data-ttu-id="f218f-150">**アセット ID**: アクティビティが実行された優先度の物理アセットのアセット ID。</span><span class="sxs-lookup"><span data-stu-id="f218f-150">**Asset ID**: The asset ID of the priority physical asset the activity was performed on.</span></span>
- <span data-ttu-id="f218f-151">**カテゴリ:** 変更されたアイテムのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="f218f-151">**Category:** The category of the item modified.</span></span> <span data-ttu-id="f218f-152">値は *、ポリシー、ケース、ユーザー、通知、設定、* および *通知テンプレートです。*</span><span class="sxs-lookup"><span data-stu-id="f218f-152">Values are *Policies, Cases, Users, Alerts, Settings,* and *Notice templates.*</span></span>
- <span data-ttu-id="f218f-153">**日付:** 組織のローカル日付と時刻に一覧表示される日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="f218f-153">**Date:** Date and time, listed in your organization's local date and time.</span></span>
- <span data-ttu-id="f218f-154">**説明**: 処理対象のオブジェクト (ポリシーや優先度のユーザー グループなど) に対してユーザーが入力した説明。</span><span class="sxs-lookup"><span data-stu-id="f218f-154">**Description**: The description input by the user for the object being acted on (such as a policy or a priority user group).</span></span>
- <span data-ttu-id="f218f-155">**DLP ポリシー**: インサイダー リスク管理ポリシーに含めるトリガーとして選択されたデータ損失防止 (DLP) ポリシー。</span><span class="sxs-lookup"><span data-stu-id="f218f-155">**DLP policy**: The data loss prevention (DLP) policy selected to trigger inclusion in an insider risk management policy.</span></span>
- <span data-ttu-id="f218f-156">**インジケーター**: アクティビティが実行されたインサイダー リスク設定内のインジケーター (インジケーターの追加や削除など)。</span><span class="sxs-lookup"><span data-stu-id="f218f-156">**Indicator**: The indicator in the within insider risk settings that the activity was performed on (such as adding or removing an indicator).</span></span>
- <span data-ttu-id="f218f-157">**通知テンプレート**: アクティビティが実行された通知テンプレート。</span><span class="sxs-lookup"><span data-stu-id="f218f-157">**Notice template**: The notice template the activity was performed on.</span></span>
- <span data-ttu-id="f218f-158">**日数 :** インサイダー リスク設定で定義されたポリシーのアクティブ化ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="f218f-158">**Number of days**: The policy activation window defined in insider risk settings.</span></span>
- <span data-ttu-id="f218f-159">**ファイル数**: Insider リスク管理設定で定義されているファイル ボリュームの制限。</span><span class="sxs-lookup"><span data-stu-id="f218f-159">**Number of files**: The file volume limit defined in insider risk management settings.</span></span>
- <span data-ttu-id="f218f-160">**ポリシー テンプレート**: インジケーターが作用したポリシー テンプレートが属します。</span><span class="sxs-lookup"><span data-stu-id="f218f-160">**Policy template**: The policy template that the indicators acted on belongs to.</span></span>
- <span data-ttu-id="f218f-161">**前の量**: ポリシーに対して以前に選択したカスタム インジケーターの量。</span><span class="sxs-lookup"><span data-stu-id="f218f-161">**Previous amount**: The previously selected custom indicator amounts for a policy.</span></span>
- <span data-ttu-id="f218f-162">**優先度ユーザー グループ**: アクティビティが実行された優先度のユーザー グループ。</span><span class="sxs-lookup"><span data-stu-id="f218f-162">**Priority user group**: The priority user group the activity was performed on.</span></span>
- <span data-ttu-id="f218f-163">**削除**: アクティビティ中に削除されたオブジェクト (ユーザー、ファイルの種類、ドメインなど)。</span><span class="sxs-lookup"><span data-stu-id="f218f-163">**Removed**: Objects that were removed during the activity, such as users, file types, or domains.</span></span>
- <span data-ttu-id="f218f-164">**Sender**: アクティビティが実行された通知テンプレートの送信者フィールド。</span><span class="sxs-lookup"><span data-stu-id="f218f-164">**Sender**: The sender field of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="f218f-165">**ターゲット ポリシー**: アクティビティが実行されたポリシー (ユーザーの追加やユーザーの削除など)。</span><span class="sxs-lookup"><span data-stu-id="f218f-165">**Target policy**: The policy the activity was performed on (such as adding a user to or removing a user from).</span></span>
- <span data-ttu-id="f218f-166">**テンプレート メッセージ本文**: アクティビティが実行された通知テンプレートのメッセージ本文。</span><span class="sxs-lookup"><span data-stu-id="f218f-166">**Template message body**: The message body of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="f218f-167">**テンプレートの** 件名 : アクティビティが実行された通知テンプレートの件名フィールド。</span><span class="sxs-lookup"><span data-stu-id="f218f-167">**Template subject**: The subject field of the notice template the activity was performed on.</span></span>
- <span data-ttu-id="f218f-168">**ユーザー:** アクティビティが実行されたユーザー。</span><span class="sxs-lookup"><span data-stu-id="f218f-168">**User:** User the activity was performed on.</span></span>
