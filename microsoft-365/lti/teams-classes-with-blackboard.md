---
title: Blackboard learn ultra Microsoft Teamsクラスを統合する
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Blackboard learn ultra Microsoft Teamsクラスを統合する
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314497"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="0d2a9-103">Blackboard learn ultra Microsoft Teamsクラスを使用する</span><span class="sxs-lookup"><span data-stu-id="0d2a9-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="0d2a9-104">チームワークは、現代のすべての組織の中核をなしています。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="0d2a9-105">コラボレーションを促進することで、成功した教育機関ごとに明確な特徴を持っています。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="0d2a9-106">Blackboard Learn Ultra のすべての機能と機能を強化するために、それらを複数のクラスとMicrosoft Teamsできます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="0d2a9-107">クラスには、リアルタイムの会話、ビデオ会議、または非同期操作が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="0d2a9-108">学生のファイル共有と共同作成エクスペリエンスを 1 か所で追加できます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="0d2a9-109">Microsoft Teamsのクラスは、教育のダイナミクスと効果的な学習の意味を再定義します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d2a9-110">学生情報システム (SIS) で [教育機関のメール] フィールドが正常に設定されたことを確認する `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span><span class="sxs-lookup"><span data-stu-id="0d2a9-110">Ensure that you have successfully set up the Institution Email field in your Student Information System (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span></span>
>
><span data-ttu-id="0d2a9-111">クラスMicrosoft Teams統合は、適切な Microsoft Azure Active Directory (AAD) ユーザー プリンシパル名 (UPN) にマップするために、SIS の教育機関の電子メール フィールドに依存します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) User Principal Name (UPN).</span></span> <span data-ttu-id="0d2a9-112">教育機関の電子メールがプロビジョニングされていない場合、これは既定で既存の電子メールに設定されます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="0d2a9-113">データが正しく同期され、Microsoft AAD と Blackboard Learn Ultra の間に電子メール データが競合しなかからなされるように、すべてのユーザーに対してこのフィールドを設定してください。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between Microsoft AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="0d2a9-114">SIS マッピングでこのフィールドを適切に設定していない場合、統合は引き続き機能しますが、作成された Teams クラスにはユーザーが表示されない可能性があります。エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="0d2a9-115">教育機関向けデータ マッピングのサポート – 教育機関の電子メール SIS フィールド</span><span class="sxs-lookup"><span data-stu-id="0d2a9-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="0d2a9-116">クラウド プロバイダー統合の進化の一環として、Blackboard Learn Ultra は、学生情報システム フレームワーク統合とパブリック REST API の両方で新しい教育機関メール フィールドを作成し、Blackboard Learn Ultra と Microsoft AAD の間でデータ同期プロセスを効果的に管理できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and Microsoft AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="0d2a9-117">教育機関の電子メールとは何を意味し、何をサポートしていますか?</span><span class="sxs-lookup"><span data-stu-id="0d2a9-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="0d2a9-118">[ **教育機関のメール]** フィールドを使用すると、クライアントの外部でサポートされているデータ ソースと Blackboard Learn Ultra の間のカスタマイズされたフィールド マッピングが可能です。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="0d2a9-119">データ ソースが Microsoft などのクラウド プロバイダーである場合、ユーザー原則名 (UPN) は、UPN プレフィックス (ユーザーのアカウント名) と、@記号と共に結合された UPN サフィックス (DNS ドメイン 名) で構成される各ユーザーのプライマリ一意識別子です。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="0d2a9-120">これにより、ユーザー内の特定のユーザーごとに一意のメール アドレスが作成Microsoft Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="0d2a9-121">データが正確で、Blackboard Learn Ultra クラスと Microsoft Teams クラス間の登録またはメンバーシップが正しく達成されるようにするには、ユーザーの電子メール アドレスが両方のシステム間で一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="0d2a9-122">Blackboard Learn Ultra では、ユーザーはユーザー インターフェイスで既存のメール アドレスを変更または上書きできます。その結果、同期エラーが発生し、ユーザーがクラス チームに正しく追加されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="0d2a9-123">Institution **Email フィールド** マッピングを使用すると、ユーザーが Blackboard Learn Ultra 内で電子メールを変更した場合でも、このレベルのセキュリティと検証チェックを正しく管理できます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="0d2a9-124">2 つの電子メール アドレスが異なる場合は、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="0d2a9-125">どのソースが優先順位を持ち、人物と教育機関の両方の電子メールとして受け取られるかについて決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="0d2a9-126">または</span><span class="sxs-lookup"><span data-stu-id="0d2a9-126">Or</span></span>
- <span data-ttu-id="0d2a9-127">インスティテューションは、インスティテューションメールでユーザー設定フィールドマッピングを設定できます。これは潜在的な競合を解決できます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="0d2a9-128">教育機関 **のメール フィールド** マッピングは、Advanced Configuration 設定 ユーザーがオブジェクト型フィールド マッピングを学習するで、**既存のすべての** SIS 統合タイプ  >    >  **で使用できます**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="0d2a9-129">インスティテューションメールは、既定ではすべての SIS 形式の Person **Email** に設定され、各ユーザーに固有である必要があります。 </span><span class="sxs-lookup"><span data-stu-id="0d2a9-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="0d2a9-130">セットアップおよび実行されている既存のすべての統合では、電子メールが重複している場合、SIS はユーザーのインポートに失敗しますので、このデータ マッピングが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="0d2a9-131">教育機関で教育機関のメールをカスタムに変更する機能が必要な場合は、SIS の [詳細構成] を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="0d2a9-132">Requirements</span><span class="sxs-lookup"><span data-stu-id="0d2a9-132">Requirements</span></span>

<span data-ttu-id="0d2a9-133">クラスMicrosoft Teams統合は **、Ultra Course View コースでのみ使用できます**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="0d2a9-134">教育機関が使用するには、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="0d2a9-135">超基本ナビゲーションを有効にした Blackboard Learn Ultra Learn SaaS を使用する</span><span class="sxs-lookup"><span data-stu-id="0d2a9-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

- <span data-ttu-id="0d2a9-136">コースで使用する LTI を有効にする。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-136">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="0d2a9-137">a.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-137">a.</span></span> <span data-ttu-id="0d2a9-138">[管理者パネル **]**  >  **[LTI ツール プロバイダー] [グローバル プロパティ** の  >  **管理] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-138">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="0d2a9-139">b.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-139">b.</span></span> <span data-ttu-id="0d2a9-140">[コース **で LTI が有効] を選択し**、必要に応じて [組織 **で有効] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-140">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="0d2a9-141">c.</span><span class="sxs-lookup"><span data-stu-id="0d2a9-141">c.</span></span> <span data-ttu-id="0d2a9-142">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-142">Select **Submit**.</span></span>

- <span data-ttu-id="0d2a9-143">LTI が構成されている必要があります</span><span class="sxs-lookup"><span data-stu-id="0d2a9-143">Must have LTI configured</span></span>

- <span data-ttu-id="0d2a9-144">Add Blackboard Learn Ultra Teams LTI Integration</span><span class="sxs-lookup"><span data-stu-id="0d2a9-144">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="0d2a9-145">Add Microsoft Teams クラス LTI 1.3 ツール</span><span class="sxs-lookup"><span data-stu-id="0d2a9-145">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="0d2a9-146">REST API ツールとクロスオリジン リソース共有の追加</span><span class="sxs-lookup"><span data-stu-id="0d2a9-146">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="0d2a9-147">クラス統合を構成Microsoft Teams承認する</span><span class="sxs-lookup"><span data-stu-id="0d2a9-147">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="0d2a9-148">Blackboard Learn Ultra Teams LTI 1.3 ツールを追加する</span><span class="sxs-lookup"><span data-stu-id="0d2a9-148">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="0d2a9-149">[管理者]**パネルで\*\*\*\*、[LTI ツール プロバイダー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-149">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="0d2a9-150">**[LTI 1.3 ツールの登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-150">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="0d2a9-151">[クライアント **ID] フィールド** に、次の ID を入力またはコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-151">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="0d2a9-152">事前に設定され、[ツールの状態] ですべての設定を確認し、[有効] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-152">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="0d2a9-153">[**インスティテューション ポリシー] で**、[**コース内の役割]、[名前**]、および [メール アドレス] を選択し、両方に **[は** い] を選択します。 </span><span class="sxs-lookup"><span data-stu-id="0d2a9-153">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="0d2a9-154">[サービス **のグレード アクセスを許可する] と** [ **メンバーシップ サービス アクセスを許可する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-154">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="0d2a9-155">[クラス LTI Microsoft Teams 1.3 ツールの追加]</span><span class="sxs-lookup"><span data-stu-id="0d2a9-155">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="0d2a9-156">[管理者]**パネルで\*\*\*\*、[LTI ツール プロバイダー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-156">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="0d2a9-157">**[LTI 1.3 ツールの登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-157">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="0d2a9-158">[クライアント **ID] フィールド** に、次の ID を入力またはコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-158">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="0d2a9-159">事前設定済みのすべての設定を確認し、[ツールの状態] で *[有効* ] を選択 *します。*</span><span class="sxs-lookup"><span data-stu-id="0d2a9-159">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="0d2a9-160">イン **スティテューション ポリシーで、[\*\*\*\*コース内の役割]、[名前]、および**[メール アドレス]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-160">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="0d2a9-161">両方に **対して [はい** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-161">Select **Yes** for both.</span></span>

6. <span data-ttu-id="0d2a9-162">[サービス **のグレード アクセスを許可する] と** [ **メンバーシップ サービス アクセスを許可する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-162">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="0d2a9-163">REST API ツールの追加</span><span class="sxs-lookup"><span data-stu-id="0d2a9-163">Add the REST API tool</span></span>

1. <span data-ttu-id="0d2a9-164">[管理者パネル **] から [** 統合] に **移動し、[Rest** **API Integrations] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-164">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="0d2a9-165">[統合 **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-165">Select **Create Integration**.</span></span>

3. <span data-ttu-id="0d2a9-166">[アプリケーション **ID] フィールド** に、次の ID を入力またはコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-166">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="0d2a9-167">この統合のユーザーを入力します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-167">Type a user for this integration.</span></span>

   <span data-ttu-id="0d2a9-168">このユーザーは、アプリケーションが関連付けられているホーム API アクセス権を持つユーザーです。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-168">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="0d2a9-169">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-169">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="0d2a9-170">クロスオリジン リソース共有の追加</span><span class="sxs-lookup"><span data-stu-id="0d2a9-170">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="0d2a9-171">[管理者] **パネルで、[** 統合] に **移動し、[**\* クロスオリジン *リソース共有] を選択します*。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-171">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="0d2a9-172">[構成 **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-172">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="0d2a9-173">**[Origin] フィールド** にコピーの種類を入力し、次の URL を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-173">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="0d2a9-174">[許可する **ヘッダー] フィールドに「承認** 」と **入力します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-174">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="0d2a9-175">[使用可能 **] を [はい** ] **に設定します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-175">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="0d2a9-176">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-176">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="0d2a9-177">グループ クラスの統合をMicrosoft Teamsおよび承認する</span><span class="sxs-lookup"><span data-stu-id="0d2a9-177">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="0d2a9-178">Blackboard Learn Ultra インスタンスを Microsoft Teams クラスと正常に統合するには、Blackboard Learn Ultra アプリケーションが Microsoft Azure テナント内でのアクセスが承認されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-178">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="0d2a9-179">これは、教育機関のグローバル管理者が完了する必要Microsoft 365プロセスです。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-179">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="0d2a9-180">このプロセスは、Blackboard Learn Ultra Instance で LTI アプリケーションを構成する前または後に実行できます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-180">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="0d2a9-181">LTI アプリケーションを構成する前に</span><span class="sxs-lookup"><span data-stu-id="0d2a9-181">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="0d2a9-182">LTI 統合を構成する前に Blackboard Learn Ultra Teams Classes Azure アプリを承認する場合は **、Microsoft Identity Platform** Admin Consent Endpoint にリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-182">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="0d2a9-183">URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-183">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="0d2a9-184">{Tenant} を **、特定** の組織の組織 ID Microsoft Azure置き換える。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-184">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="0d2a9-185">LTI アプリケーションの構成後</span><span class="sxs-lookup"><span data-stu-id="0d2a9-185">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="0d2a9-186">[管理者 **] パネルで、[** ツールとユーティリティ] に移動 **し**、[統合管理者] **Microsoft Teamsを選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-186">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="0d2a9-187">[有効 **にする] をMicrosoft Teams** します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-187">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="0d2a9-188">使用可能な **テキスト フィールドに Microsoft テナント ID** を追加します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-188">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="0d2a9-189">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-189">Choose one of the following options:</span></span>

   - <span data-ttu-id="0d2a9-190">アプリに事前同意がある場合は、小さなチェックマークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-190">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="0d2a9-191">チェックマークが表示された場合は、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-191">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="0d2a9-192">同意が承認されていない場合は、説明されている手順に従って、同意の URL を生成し、承認のためにグローバル管理者Microsoft 365に送信します。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-192">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="0d2a9-193">承認の確認が完了したら、[再試行] を選択 **して** 確認し、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d2a9-193">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>