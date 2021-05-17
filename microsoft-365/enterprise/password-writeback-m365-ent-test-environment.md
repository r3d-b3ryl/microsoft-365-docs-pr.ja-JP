---
title: Microsoft 365 テスト環境のパスワードの書き戻し
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境用のパスワードの書き戻しを構成する。'
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921482"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="86db9-103">Microsoft 365 テスト環境のパスワードの書き戻し</span><span class="sxs-lookup"><span data-stu-id="86db9-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="86db9-104">*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="86db9-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="86db9-105">ユーザーはパスワード の書き戻しを使用して、Azure Active Directory (Azure AD) を使用してパスワードを更新し、ローカルの Active Directory ドメイン サービス (AD DS) にレプリケートできます。</span><span class="sxs-lookup"><span data-stu-id="86db9-105">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="86db9-106">パスワードの書き戻しを使用すると、ユーザーは、元のユーザー アカウントが保存されているオンプレミスの DS ADパスワードを更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="86db9-106">With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="86db9-107">これにより、オンプレミス ネットワークへのリモート アクセス接続を持たなかったローミングユーザーまたはリモート ユーザーが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="86db9-107">This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="86db9-108">この記事では、パスワードの書き戻しMicrosoft 365テスト環境を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="86db9-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="86db9-109">パスワード ライトバック用にテスト環境を構成するには、次の 2 つのフェーズが必要です。</span><span class="sxs-lookup"><span data-stu-id="86db9-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="86db9-110">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="86db9-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="86db9-111">フェーズ 2: TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。</span><span class="sxs-lookup"><span data-stu-id="86db9-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="86db9-113">エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="86db9-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="86db9-114">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="86db9-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="86db9-115">最初に、パスワード ハッシュ同期の手順 [に従います](password-hash-sync-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="86db9-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="86db9-116">結果の構成は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="86db9-116">Your resulting configuration looks like this:</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="86db9-118">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="86db9-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="86db9-119">Microsoft 365 E5 の試用版または有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="86db9-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="86db9-120">Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。</span><span class="sxs-lookup"><span data-stu-id="86db9-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="86db9-121">Azure AD Connect が APP1 上で実行され、TESTLAB AD DS ドメインが、Microsoft 365 サブスクリプションの Azure AD テナントに同期されます。</span><span class="sxs-lookup"><span data-stu-id="86db9-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="86db9-122">フェーズ 2: TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。</span><span class="sxs-lookup"><span data-stu-id="86db9-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="86db9-123">まずはじめに、User 1 をグローバル管理者ロールとして構成します。</span><span class="sxs-lookup"><span data-stu-id="86db9-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="86db9-124">[Microsoft 365 管理センター](https://portal.microsoft.com)から、全体管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="86db9-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="86db9-125">[アクティブ **ユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="86db9-126">[アクティブ な **ユーザー] ページ** で **、user1 アカウントを選択** します。</span><span class="sxs-lookup"><span data-stu-id="86db9-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="86db9-127">[ユーザー **1] ウィンドウで** 、[役割] の **横にある [編集** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="86db9-128">user1 の **[ユーザー 役割の編集**] ウィンドウで、[グローバル管理者] を選択し、[保存]**を選択\*\*\*\*し**、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="86db9-129">次に、TESTLAB AD DS ドメインで他のユーザーの代理としてパスワードを変更できるように、User 1 アカウント のセキュリティ設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="86db9-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="86db9-130">[[Azure ポータル](https://portal.azure.com)] からグローバル管理者アカウントでサインインし、TESTLAB\User1 アカウントで APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="86db9-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="86db9-131">APP1 のデスクトップから、[スタート] を選択 **し**、[アクティブ] と **入力** し **、[Active Directory ユーザーとコンピューター] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="86db9-132">メニュー バーで、[表示] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="86db9-133">高度 **な機能が** 有効になっていない場合は、その機能を選択して有効にします。</span><span class="sxs-lookup"><span data-stu-id="86db9-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="86db9-134">ツリー ウィンドウで、ドメインを選択して保持 (または右クリック) し、[プロパティ] を選択し、[セキュリティ] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="86db9-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="86db9-135">**[詳細設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="86db9-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="86db9-136">[アクセス許可 **] タブで** 、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="86db9-137">[**プリンシパルの選択] を選択し\*\*\*\*、「User1」と入力** し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="86db9-138">[**適用先**] で、[**ユーザーの子孫オブジェクト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="86db9-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="86db9-139">[**アクセス許可**] で、次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="86db9-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="86db9-140">**[パスワードの変更]**</span><span class="sxs-lookup"><span data-stu-id="86db9-140">**Change password**</span></span>
    - <span data-ttu-id="86db9-141">**パスワードのリセット**</span><span class="sxs-lookup"><span data-stu-id="86db9-141">**Reset password**</span></span>

10. <span data-ttu-id="86db9-142">[**プロパティ**] で、次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="86db9-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="86db9-143">**LockoutTime の書き込み**</span><span class="sxs-lookup"><span data-stu-id="86db9-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="86db9-144">**pwdLastSet の書き込み**</span><span class="sxs-lookup"><span data-stu-id="86db9-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="86db9-145">**[OK] を** 3 回選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="86db9-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="86db9-146">[**Active Directory ユーザーとコンピューター**] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="86db9-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="86db9-147">次に、APP1 で、パスワード書き戻し用の Azure AD Connect を構成します。</span><span class="sxs-lookup"><span data-stu-id="86db9-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="86db9-148">必要に応じて、TESTLAB\User1 アカウントを使用して APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="86db9-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="86db9-149">APP1 のデスクトップで、[**Azure AD Connect**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="86db9-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="86db9-150">[ようこそ] **ページで、[** 構成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="86db9-151">[追加タスク **] ページで** 、[同期オプションの **カスタマイズ] を選択し**、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="86db9-152">[Azure **Connect] ページで** AD管理者アカウントの資格情報を入力し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="86db9-153">[ディレクトリ] **Connect[\*\*\*\*ドメイン/OU フィルター] ページで、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="86db9-154">[オプション機能 **] ページで** 、[パスワードの書き **戻し] を選択し**、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="86db9-155">[構成の **準備完了] ページで、[** 構成] **を選択し** 、プロセスが完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="86db9-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="86db9-156">構成が完了したら、[終了] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="86db9-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="86db9-157">これで、シミュレートされたイントラネットの仮想ネットワークに接続されていないコンピューター上のユーザーのパスワード ライトバックをテストする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="86db9-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="86db9-158">結果の構成は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="86db9-158">Your resulting configuration looks like this:</span></span>

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="86db9-160">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="86db9-160">This configuration consists of:</span></span>

- <span data-ttu-id="86db9-161">TESTLAB Microsoft 365 E5試用版または有料サブスクリプションをDNS ドメインします。\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="86db9-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="86db9-162">が登録されている Microsoft 365 E5 または Office 365 E5 の試用版サブスクリプションまたは有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="86db9-162">registered.</span></span>
- <span data-ttu-id="86db9-163">Azure 仮想ネットワークのサブネット上の DC1、APP1、および CLIENT1 仮想マシンで構成される、インターネットに接続された簡略化された組織イントラネット。</span><span class="sxs-lookup"><span data-stu-id="86db9-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="86db9-164">Azure AD Connect が APP1 上で実行され、Microsoft 365 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。</span><span class="sxs-lookup"><span data-stu-id="86db9-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="86db9-165">パスワードの書き戻しが有効になっているため、ユーザーは簡略化されたイントラネットに接続せずに、Azure AD 経由でパスワードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="86db9-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="86db9-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="86db9-166">Next step</span></span>

<span data-ttu-id="86db9-167">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="86db9-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="86db9-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="86db9-168">See also</span></span>

[<span data-ttu-id="86db9-169">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="86db9-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="86db9-170">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="86db9-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="86db9-171">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="86db9-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)