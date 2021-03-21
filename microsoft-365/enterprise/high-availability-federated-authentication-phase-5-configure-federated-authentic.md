---
title: 高可用性フェデレーション認証 フェーズ 5 Microsoft 365 のフェデレーション認証を構成する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: '概要: Microsoft Azure AD Microsoft 365 の高可用性フェデレーション認証用に Azure AD Connect を構成します。'
ms.openlocfilehash: 2bca2b758486b85d185870e2e14b495b8f084cb7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929410"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a><span data-ttu-id="96597-103">高可用性フェデレーション認証 フェーズ 5: Microsoft 365 のフェデレーション認証を構成する</span><span class="sxs-lookup"><span data-stu-id="96597-103">High availability federated authentication Phase 5: Configure federated authentication for Microsoft 365</span></span>

<span data-ttu-id="96597-104">Azure インフラストラクチャ サービスに Microsoft 365 の高可用性フェデレーション認証を展開するこの最終フェーズでは、パブリック証明機関によって発行された証明書を取得してインストールし、構成を確認してから、ディレクトリ同期サーバーに Azure AD Connect をインストールして実行します。</span><span class="sxs-lookup"><span data-stu-id="96597-104">In this final phase of deploying high availability federated authentication for Microsoft 365 in Azure infrastructure services, you get and install a certificate issued by a public certification authority, verify your configuration, and then install and run Azure AD Connect on the directory synchronization server.</span></span> <span data-ttu-id="96597-105">Azure AD Connect は、Microsoft 365 サブスクリプションと Active Directory フェデレーション サービス (AD FS) と Web アプリケーション プロキシ サーバーをフェデレーション認証用に構成します。</span><span class="sxs-lookup"><span data-stu-id="96597-105">Azure AD Connect configures your Microsoft 365 subscription and your Active Directory Federation Services (AD FS) and web application proxy servers for federated authentication.</span></span>
  
<span data-ttu-id="96597-106">すべての [フェーズについては、「Azure での Microsoft 365](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) の高可用性フェデレーション認証の展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96597-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a><span data-ttu-id="96597-107">パブリック証明書を取得し、ディレクトリ同期サーバーにコピーする</span><span class="sxs-lookup"><span data-stu-id="96597-107">Get a public certificate and copy it to the directory synchronization server</span></span>

<span data-ttu-id="96597-108">次のプロパティを使用して、公開証明機関からデジタル証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="96597-108">Get a digital certificate from a public certification authority with the following properties:</span></span>
  
- <span data-ttu-id="96597-109">SSL 接続の作成に適した X.509 証明書。</span><span class="sxs-lookup"><span data-stu-id="96597-109">An X.509 certificate suitable for creating SSL connections.</span></span>
    
- <span data-ttu-id="96597-110">サブジェクトの別名 (SAN) の拡張プロパティは、フェデレーション サービス FQDN に設定されています (例: fs.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="96597-110">The Subject Alternative Name (SAN) extended property is set to your federation service FQDN (example: fs.contoso.com).</span></span>
    
- <span data-ttu-id="96597-111">証明書には、秘密キーを PFX 形式で格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96597-111">The certificate must have the private key and be stored in PFX format.</span></span>
    
<span data-ttu-id="96597-p102">さらに、組織のコンピューターとデバイスでデジタル証明書を発行した公開証明機関を信頼する必要があります。この信頼を確立するには、コンピューターとデバイス上の信頼されたルート証明機関ストアに、公開証明機関から取得したルート証明書をインストールします。通常、Microsoft Windows を実行するコンピューターには、一般的に使用される証明機関が発行したこれらの種類の証明書セットがインストールされています。公開証明機関のルート証明書がまだインストールされていない場合は、この証明書を組織のコンピューターとデバイスに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96597-p102">Additionally, your organization computers and devices must trust the public certification authority that is issuing the digital certificate. This trust is established by having a root certificate from the public certification authority installed in the trusted root certification authorities store on your computers and devices. Computers running Microsoft Windows typically have a set of these types of certificates installed from commonly-used certification authorities. If the root certificate from your public certification authority is not already installed, you must deploy this to the computers and devices of your organization.</span></span>
  
<span data-ttu-id="96597-116">フェデレーション認証の証明書要件に関する詳細については、「[フェデレーションのインストールと構成の前提条件](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96597-116">For more information about certificate requirements for federated authentication, see [Prerequisites for federation installation and configuration](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).</span></span>
  
<span data-ttu-id="96597-117">証明書を受け取った場合は、ディレクトリ同期サーバーの C: ドライブ上のフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="96597-117">When you receive the certificate, copy it to a folder on the C: drive of the directory synchronization server.</span></span> <span data-ttu-id="96597-118">たとえば、ファイルに SSL.pfx という名前を付け、ディレクトリ同期サーバーの C: \\ Certs フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="96597-118">For example, name the file SSL.pfx and store it in the C:\\Certs folder on the directory synchronization server.</span></span>
  
## <a name="verify-your-configuration"></a><span data-ttu-id="96597-119">構成を確認する</span><span class="sxs-lookup"><span data-stu-id="96597-119">Verify your configuration</span></span>

<span data-ttu-id="96597-120">これで、Microsoft 365 の Azure ADフェデレーション認証を構成する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="96597-120">You should now be ready to configure Azure AD Connect and federated authentication for Microsoft 365.</span></span> <span data-ttu-id="96597-121">確認用のチェックリストを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="96597-121">To ensure that you are, here is a checklist:</span></span>
  
- <span data-ttu-id="96597-122">組織のパブリック ドメインが Microsoft 365 サブスクリプションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="96597-122">Your organization's public domain is added to your Microsoft 365 subscription.</span></span>
    
- <span data-ttu-id="96597-123">組織の Microsoft 365 ユーザー アカウントは、組織のパブリック ドメイン名に構成され、正常にサインインできます。</span><span class="sxs-lookup"><span data-stu-id="96597-123">Your organization's Microsoft 365 user accounts are configured to your organization's public domain name and can successfully sign in.</span></span>
    
- <span data-ttu-id="96597-124">フェデレーション サービス FQDN をパブリック ドメイン名に基づいて決定している。</span><span class="sxs-lookup"><span data-stu-id="96597-124">You have determined a federation service FQDN based your public domain name.</span></span>
    
- <span data-ttu-id="96597-125">フェデレーション サービス FQDN のパブリック DNS A レコードが、Web アプリケーション プロキシ サーバー用の Azure インターネット接続ロード バランサーのパブリック IP アドレスを指している。</span><span class="sxs-lookup"><span data-stu-id="96597-125">A public DNS A record for your federation service FQDN points to the public IP address of the Internet-facing Azure load balancer for the web application proxy servers.</span></span>
    
- <span data-ttu-id="96597-126">フェデレーション サービス FQDN のプライベート DNS A レコードが、AD FS サーバー用の内部の Azure ロード バランサーのプライベート IP アドレスを指している。</span><span class="sxs-lookup"><span data-stu-id="96597-126">A private DNS A record for your federation service FQDN points to the private IP address of the internal Azure load balancer for the AD FS servers.</span></span>
    
- <span data-ttu-id="96597-127">SAN をフェデレーション サービス FQDN に設定した SSL 接続に適した公的証明機関-isssued デジタル証明書は、ディレクトリ同期サーバーに保存されている PFX ファイルです。</span><span class="sxs-lookup"><span data-stu-id="96597-127">A public certification authority-isssued digital certificate suitable for SSL connections with the SAN set to your federation service FQDN is a PFX file stored on your directory synchronization server.</span></span>
    
- <span data-ttu-id="96597-128">公的証明機関のルート証明書が、コンピューターとデバイスの信頼されたルート証明機関ストアにインストールされている。</span><span class="sxs-lookup"><span data-stu-id="96597-128">The root certificate for the public certification authority is installed in the Trusted Root Certification Authorities store on your computers and devices.</span></span>
    
<span data-ttu-id="96597-129">Contoso 組織の例を、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="96597-129">Here is an example for the Contoso organization:</span></span>
  
<span data-ttu-id="96597-130">**Azure での高可用性フェデレーション認証インフラストラクチャの構成例**</span><span class="sxs-lookup"><span data-stu-id="96597-130">**An example configuration for a high availability federated authentication infrastructure in Azure**</span></span>

![Azure での高可用性 Microsoft 365 フェデレーション認証インフラストラクチャの構成例](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a><span data-ttu-id="96597-132">Azure AD Connect を実行してフェデレーション認証を構成する</span><span class="sxs-lookup"><span data-stu-id="96597-132">Run Azure AD Connect to configure federated authentication</span></span>

<span data-ttu-id="96597-133">Azure AD接続ツールは、AD FS サーバー、Web アプリケーション プロキシ サーバー、および Microsoft 365 をフェデレーション認証用に構成します。</span><span class="sxs-lookup"><span data-stu-id="96597-133">The Azure AD Connect tool configures the AD FS servers, the web application proxy servers, and Microsoft 365 for federated authentication with these steps:</span></span>
  
1. <span data-ttu-id="96597-134">ローカル管理者特権を持つドメイン アカウントを使用して、ディレクトリ同期サーバーへのリモート デスクトップ接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="96597-134">Create a remote desktop connection to your directory synchronization server with a domain account that has local administrator privileges.</span></span>
    
2. <span data-ttu-id="96597-135">ディレクトリ同期サーバーのデスクトップから、ディレクトリを開Internet Explorerに移動します [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 。</span><span class="sxs-lookup"><span data-stu-id="96597-135">From the desktop of the directory synchronization server, open Internet Explorer and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
3. <span data-ttu-id="96597-136">**[Microsoft Azure Active Directory Connect]** ページで、 **[ダウンロード]** をクリックしてから **[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-136">On the **Microsoft Azure Active Directory Connect** page, click **Download**, and then click **Run**.</span></span>
    
4. <span data-ttu-id="96597-137">**[Azure AD Connect へようこそ]** ページで、 **[同意する]** をクリックしてから、 **[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-137">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue.**</span></span>
    
5. <span data-ttu-id="96597-138">**[簡単設定]** ページで、**[カスタマイズ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-138">On the **Express Settings** page, click **Customize**.</span></span>
    
6. <span data-ttu-id="96597-139">**[必須コンポーネントのインストール]** ページで、**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-139">On the **Install required components** page, click **Install**.</span></span>
    
7. <span data-ttu-id="96597-140">**[ユーザー サインイン]** ページで、**[AD FS とのフェデレーション]** をクリックしてから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-140">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="96597-141">[Azure **への接続] AD、Microsoft** 365 サブスクリプションのグローバル管理者アカウントの名前とパスワードを入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="96597-141">On the **Connect to Azure AD** page, type the name and password of a global administrator account for your Microsoft 365 subscription, and then click **Next**.</span></span>
    
9. <span data-ttu-id="96597-142">[ディレクトリ **の接続**] ページで、フォレストでオンプレミスの Active Directory ドメイン サービス (AD DS) フォレストが選択されていないことを確認し、ドメイン管理者アカウントの名前とパスワードを入力し、[ディレクトリの追加] をクリックし、[次へ] をクリックします。  </span><span class="sxs-lookup"><span data-stu-id="96597-142">On the **Connect your directories** page, ensure that your on-premises Active Directory Domain Services (AD DS) forest is selected in **Forest**, type the name and password of a domain administrator account, click **Add Directory**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="96597-143">**[Azure AD サインインの構成]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-143">On the **Azure AD sign-in configuration** page, click **Next**.</span></span>
    
11. <span data-ttu-id="96597-144">**[ドメインと OU のフィルタリング]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-144">On the **Domain and OU filtering** page, click **Next**.</span></span>
    
12. <span data-ttu-id="96597-145">**[一意のユーザー識別]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-145">On the **Uniquely identifying your users** page, click **Next**.</span></span>
    
13. <span data-ttu-id="96597-146">**[ユーザーおよびデバイスのフィルタリング]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-146">On the **Filter users and devices** page, click **Next**.</span></span>
    
14. <span data-ttu-id="96597-147">**[オプション機能]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-147">On the **Optional features** page, click **Next**.</span></span>
    
15. <span data-ttu-id="96597-148">**[AD FS ファーム]** ページで、 **[新しい AD FS ファームを構成する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-148">On the **AD FS farm** page, click **Configure a new AD FS farm**.</span></span>
    
16. <span data-ttu-id="96597-149">**[参照]** をクリックして、公開証明機関から取得した SSL 証明書の場所と名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="96597-149">Click **Browse** and specify the location and name of the SSL certificate from the public certification authority.</span></span>
    
17. <span data-ttu-id="96597-150">確認する画面が表示されたら、証明書のパスワードを入力して、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-150">When prompted, type the certificate password, and then click **OK**.</span></span>
    
18. <span data-ttu-id="96597-151">**[サブジェクト名]** と **[フェデレーション サービス名]** がフェデレーション サービス FQDN に設定されていることを確認して、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-151">Verify that the **Subject Name** and **Federation Service Name** are set to your federation service FQDN, and then click **Next**.</span></span>
    
19. <span data-ttu-id="96597-152">**[AD FS サーバー]** ページで、最初の AD FS サーバーの名前 (「表 M」-「項目 4」-「仮想マシン名」列) を入力し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-152">On the **AD FS servers** page, type your first AD FS server's name (Table M - Item 4 - Virtual machine name column), and then click **Add**.</span></span>
    
20. <span data-ttu-id="96597-153">2 番目の AD FS サーバーの名前 (「表 M」-「項目 5」-「仮想マシン名」列) を入力し、 **[追加]** をクリックしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-153">Type your second AD FS server's name (Table M - Item 5 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
21. <span data-ttu-id="96597-154">**[Web アプリケーション プロキシ サーバー]** ページで、最初の Web アプリケーション プロキシ サーバーの名前 (「表 M」-「項目 6」-「仮想マシン名」列) を入力し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-154">On the **Web Application Proxy servers** page, type your first web application proxy server's name (Table M - Item 6 - Virtual machine name column), and then click **Add**.</span></span>
    
22. <span data-ttu-id="96597-155">2 番目の Web アプリケーション プロキシ サーバーの名前 (「表 M」-「項目 7」-「仮想マシン名」列) を入力し、 **[追加]** をクリックしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-155">Type your second web application proxy server's name (Table M - Item 7 - Virtual machine name column), click **Add**, and then click **Next**.</span></span>
    
23. <span data-ttu-id="96597-156">**[ドメイン管理者の資格情報]** ページで、ドメイン管理者アカウントのユーザー名とパスワードを入力し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-156">On the **Domain Administrator credentials** page, type the user name and password of a domain administrator account, and then click **Next**.</span></span>
    
24. <span data-ttu-id="96597-157">**[AD FS サービス アカウント]** ページで、エンタープライズ管理者アカウントのユーザー名とパスワードを入力し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-157">On the **AD FS service account** page, type the user name and password of an enterprise administrator account, and then click **Next**.</span></span>
    
25. <span data-ttu-id="96597-158">**[Azure AD ドメイン]** ページの **[ドメイン]** で、組織の DNS ドメイン名を選択して、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-158">On the **Azure AD Domain** page, in **Domain**, select your organization's DNS domain name, and then click **Next**.</span></span>
    
26. <span data-ttu-id="96597-159">**[構成の準備完了]** ページで、 **[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-159">On the **Ready to configure** page, click **Install**.</span></span>
    
27. <span data-ttu-id="96597-p105">**[インストールの完了]** ページで **[確認]** をクリックします。イントラネット構成とインターネット構成の両方が正常に確認されたことを示す 2 つのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96597-p105">On the **Installation complete** page, click **Verify**. You should see two messages indicating that both the intranet and Internet configuration was successfully verified.</span></span>
    
  - <span data-ttu-id="96597-162">イントラネット メッセージには、AD FS サーバー用の Azure 内部ロード バランサーのプライベート IP アドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="96597-162">The intranet message should list the private IP address of your Azure internal load balancer for your AD FS servers.</span></span>
    
  - <span data-ttu-id="96597-163">インターネット メッセージには、Web アプリケーション プロキシ サーバー用の Azure インターネット接続ロード バランサーのパブリック IP アドレスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="96597-163">The Internet message should list the public IP address of your Azure Internet-facing load balancer for your web application proxy servers.</span></span>
    
28. <span data-ttu-id="96597-164">**[インストールの完了]** ページで、 **[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96597-164">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="96597-165">サーバーのプレース ホルダー名を使用した、最終構成がこちらです。</span><span class="sxs-lookup"><span data-stu-id="96597-165">Here is the final configuration, with placeholder names for the servers.</span></span>
  
<span data-ttu-id="96597-166">**フェーズ 5:Azure での高可用性フェデレーション認証インフラストラクチャの最終構成**</span><span class="sxs-lookup"><span data-stu-id="96597-166">**Phase 5: The final configuration of a high availability federated authentication infrastructure in Azure**</span></span>

![Azure での高可用性 Microsoft 365 フェデレーション認証インフラストラクチャの最終的な構成](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="96597-168">Azure での Microsoft 365 の高可用性フェデレーション認証インフラストラクチャが完了しました。</span><span class="sxs-lookup"><span data-stu-id="96597-168">Your high availability federated authentication infrastructure for Microsoft 365 in Azure is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="96597-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="96597-169">See Also</span></span>

[<span data-ttu-id="96597-170">Azure に Microsoft 365 の高可用性フェデレーション認証を展開する</span><span class="sxs-lookup"><span data-stu-id="96597-170">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="96597-171">Microsoft 365 開発/テスト環境のフェデレーション ID</span><span class="sxs-lookup"><span data-stu-id="96597-171">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="96597-172">Microsoft 365 ソリューションおよびアーキテクチャ センター</span><span class="sxs-lookup"><span data-stu-id="96597-172">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)

[<span data-ttu-id="96597-173">Microsoft 365 のフェデレーション ID</span><span class="sxs-lookup"><span data-stu-id="96597-173">Federated identity for Microsoft 365</span></span>](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)