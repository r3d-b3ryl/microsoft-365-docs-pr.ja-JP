---
title: Microsoft 365 テスト環境のパスワードの書き戻し
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: '概要: Microsoft 365 テスト環境用のパスワードの書き戻しを構成する。'
ms.openlocfilehash: 13fffb595595269b627a1cc499558796c6306205
ms.sourcegitcommit: dbcc32218489ab256b7eb343290fcccb9bc04e36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/02/2019
ms.locfileid: "33553346"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="15b7f-103">Microsoft 365 テスト環境のパスワードの書き戻し</span><span class="sxs-lookup"><span data-stu-id="15b7f-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="15b7f-p101">ユーザーが Azure Active Directory (Azure AD) からパスワードを更新できるようにします。更新されたパスワードはローカルの Active Directory Domain Services (AD DS) にレプリケートされます。パスワードの書き戻しにより、ユーザーは元のユーザー アカウントが保存されているオンプレミスの AD DS でパスワードを更新する必要がなくなります。オンプレミス ネットワークにリモート アクセス接続できないローミング ユーザーやリモート ユーザーにとって便利な機能です。</span><span class="sxs-lookup"><span data-stu-id="15b7f-p101">Password writeback allows users to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="15b7f-107">この記事では、Microsoft 365 テスト環境でのパスワード書き戻しを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-107">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="15b7f-108">設定は 2 つのフェーズで行います。</span><span class="sxs-lookup"><span data-stu-id="15b7f-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="15b7f-109">パスワード ハッシュ同期を実装するシミュレーションのエンタープライズ Microsoft 365 テスト環境を作成する。</span><span class="sxs-lookup"><span data-stu-id="15b7f-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="15b7f-110">TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。</span><span class="sxs-lookup"><span data-stu-id="15b7f-110">Enable password writeback for the TESTLAB AD DS domain.</span></span>
    
![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="15b7f-112">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="15b7f-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="15b7f-113">フェーズ 1: Microsoft 365 テスト環境のパスワード ハッシュ同期を構成する</span><span class="sxs-lookup"><span data-stu-id="15b7f-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="15b7f-p102">まず、「[パスワード ハッシュの同期](password-hash-sync-m365-ent-test-environment.md)」の手順に従います。最終的な構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15b7f-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![パスワード ハッシュ同期を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="15b7f-117">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="15b7f-118">Office 365 E5 および EMS E5 の試用版サブスクリプションまたは有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="15b7f-118">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="15b7f-119">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="15b7f-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="15b7f-120">Azure AD Connect が APP1 上で実行され、TESTLAB AD DS ドメインが、Office 365 および EMS E5 サブスクリプションの Azure AD テナントに同期されます。</span><span class="sxs-lookup"><span data-stu-id="15b7f-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="15b7f-121">フェーズ 2: TESTLAB AD DS ドメイン へのパスワードの書き戻しを有効にする。</span><span class="sxs-lookup"><span data-stu-id="15b7f-121">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="15b7f-122">まずはじめに、User 1 をグローバル管理者ロールとして構成します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-122">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="15b7f-123">[Microsoft 365 管理センター](https://portal.microsoft.com)から、全体管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-123">Sign in to the Microsoft 365 admin center (  ) with your global administrator account.</span></span>

2. <span data-ttu-id="15b7f-124">**[アクティブなユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-124">Click **Active users**.</span></span>
 
3. <span data-ttu-id="15b7f-125">[**アクティブなユーザー**] ページで、[**user1**] アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-125">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="15b7f-126">[**User1**] ウィンドウで、[**役割**] の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-126">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="15b7f-p103">user1 の [**ユーザー役割の編集**] ウィンドウで、[**グローバル管理者**] をクリックします。[**保存**] をクリックし、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-p103">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="15b7f-129">次に、TESTLAB AD DS ドメインで他のユーザーの代理としてパスワードを変更できるように、User 1 アカウント のセキュリティ設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="15b7f-130">[[Azure ポータル](https://portal.azure.com)] からグローバル管理者アカウントでサインインし、TESTLAB\User1 アカウントで APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="15b7f-131">APP1 のデスクトップで [**開始**] をクリックして [**active**] と入力し、[**Active Directory ユーザーとコンピューター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-131">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="15b7f-p104">メニュー バーで [**表示**] をクリックします。[**高度な機能**] が有効になっていない場合は、クリックして有効にします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-p104">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="15b7f-134">ツリー ウィンドウでドメインを右クリックし、[**プロパティ**] をクリックします。次に、[**セキュリティ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-134">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="15b7f-135">[**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-135">Click **Advanced**.</span></span>

6. <span data-ttu-id="15b7f-136">[**アクセス許可**] タブで [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-136">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="15b7f-137">[**プリンシパルの選択**] をクリックし、 [**User1**] と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-137">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="15b7f-138">[**適用先**] で、[**ユーザーの子孫オブジェクト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="15b7f-139">[**アクセス許可**] で、次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="15b7f-140">パスワードの変更</span><span class="sxs-lookup"><span data-stu-id="15b7f-140">Change password</span></span>
    - <span data-ttu-id="15b7f-141">パスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="15b7f-141">Reset password</span></span>

10. <span data-ttu-id="15b7f-142">[**プロパティ**] で、次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="15b7f-143">LockoutTime の書き込み</span><span class="sxs-lookup"><span data-stu-id="15b7f-143">Write lockoutTime</span></span>
    - <span data-ttu-id="15b7f-144">pwdLastSet の書き込み</span><span class="sxs-lookup"><span data-stu-id="15b7f-144">Write pwdLastSet</span></span>

11. <span data-ttu-id="15b7f-145">[**OK**] を 3 回クリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-145">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="15b7f-146">[**Active Directory ユーザーとコンピューター**] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="15b7f-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="15b7f-147">次に、APP1 で、パスワード書き戻し用の Azure AD Connect を構成します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="15b7f-148">必要に応じて、TESTLAB\User1 アカウントを使用して APP1 に接続します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="15b7f-149">APP1 のデスクトップで、[**Azure AD Connect**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="15b7f-150">[**ようこそ**] ページで、[**構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-150">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="15b7f-151">[**追加のタスク**] ページで [**同期オプションのカスタマイズ**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-151">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="15b7f-152">**[Azure AD に接続]** ページで、グローバル管理者の資格情報を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-152">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="15b7f-153">[**ディレクトリの接続**] ページと [**ドメインと OU のフィルタ リング**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-153">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="15b7f-154">**[オプション機能]** ページで、**[パスワードの書き戻し]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-154">On the **Optional features** page, select **Password writeback** and click **Next**.</span></span> 

8. <span data-ttu-id="15b7f-155">[**構成の準備完了**] ページで [**構成**] をクリックし、処理が完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="15b7f-155">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="15b7f-156">構成の完了が表示されたら、[**終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15b7f-156">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="15b7f-157">これで、シミュレートされたイントラネットの仮想ネットワークに接続されていないコンピューター上のユーザーに対してパスワードの書き戻しをテストする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="15b7f-157">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="15b7f-158">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-158">Here is your resulting configuration:</span></span>

![パススルー認証を実装するシミュレーション エンタープライズ テスト環境](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="15b7f-160">この構成は、次の内容で成立します。</span><span class="sxs-lookup"><span data-stu-id="15b7f-160">This configuration consists of:</span></span>

- <span data-ttu-id="15b7f-161">DNS ドメイン TESTLAB.\<ドメイン名> が登録されている Office 365 E5 および EMS E5 の試用版サブスクリプションまたは有料サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="15b7f-161">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="15b7f-162">インターネットに接続する組織の簡易型イントラネット。Azure 仮想ネットワークのサブネット上に配置された仮想マシン DC1、APP1、および CLIENT1 で構成されます。</span><span class="sxs-lookup"><span data-stu-id="15b7f-162">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="15b7f-163">Azure AD Connect が APP1 上で実行され、Office 365 および EMS E5 サブスクリプションの Azure AD テナントから、アカウントおよびグループのリストが TESTLAB AD DS ドメインに同期されます。</span><span class="sxs-lookup"><span data-stu-id="15b7f-163">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="15b7f-164">パスワードの書き戻しが有効になっているため、ユーザーは簡略化されたイントラネットに接続せずに、Azure AD 経由でパスワードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="15b7f-164">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

<span data-ttu-id="15b7f-165">実稼働環境でのパスワードの書き戻しの構成に関する情報およびリンクについては、ID フェーズの手順、「[パスワードの更新を簡素化する](identity-password-reset.md#identity-pw-writeback)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15b7f-165">See the [Simplify password updates](identity-password-reset.md#identity-pw-writeback) step in the Identity phase for information and links to configure password writeback in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="15b7f-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="15b7f-166">Next step</span></span>

<span data-ttu-id="15b7f-167">テスト環境の追加の [ID](m365-enterprise-test-lab-guides.md#identity) 機能について調べます。</span><span class="sxs-lookup"><span data-stu-id="15b7f-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="15b7f-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="15b7f-168">See also</span></span>

[<span data-ttu-id="15b7f-169">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="15b7f-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="15b7f-170">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="15b7f-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="15b7f-171">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="15b7f-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


