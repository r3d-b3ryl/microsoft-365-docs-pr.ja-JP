---
title: 複数地域環境での Exchange Online メールボックスの管理
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: PowerShell を使用して Microsoft 365 環境の Exchange Online の複数地域設定を管理する方法について説明します。
ms.openlocfilehash: 996566d67aa8ba7ebca1406cd5d6265458637fee
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546248"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="f0ae1-103">複数地域環境での Exchange Online メールボックスの管理</span><span class="sxs-lookup"><span data-stu-id="f0ae1-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="f0ae1-104">Microsoft 365 環境で複数の geo プロパティを表示および構成するには、Exchange Online PowerShell が必要です。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="f0ae1-105">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="f0ae1-106">ユーザー オブジェクトの **PreferredDataLocation** プロパティを参照するには、v1.x に [Microsoft Azure Active Directory PowerShell モジュール](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="f0ae1-107">AAD Connect 経由で AAD に同期されたユーザー オブジェクトでは、**PreferredDataLocation** 値を AAD PowerShell 経由で直接変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="f0ae1-108">クラウド専用ユーザー オブジェクトは、AAD PowerShell 経由で変更できます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="f0ae1-109">Azure AD PowerShell に接続するには、「[PowerShell への接続](connect-to-microsoft-365-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="f0ae1-110">Exchange Online PowerShell を使用して、地域の場所に直接接続する</span><span class="sxs-lookup"><span data-stu-id="f0ae1-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="f0ae1-111">通常、Exchange Online PowerShellは地理上の中央位置に接続します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="f0ae1-112">しかし、衛星の地理的位置に直接接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="f0ae1-113">パフォーマンスが向上するため、その場所にいるユーザーのみを管理している場合は、衛星地域に直接接続することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="f0ae1-114">EXO V2 モジュールをインストールして使用するための要件は、「[EXO V2 モジュールをインストールして維持する](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="f0ae1-115">Exchange Online の PowerShell を特定の地域の場所に接続するために、 *Connectionuri* パラメーターは通常の接続手順とは異なります。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="f0ae1-116">残りのコマンドと値は同じです。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="f0ae1-117">具体的には、 `?email=<emailaddress>` _connectionuri_ 値の末尾に値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="f0ae1-118">`<emailaddress>` は、対象と **なる** 地域の場所にあるメールボックスの電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="f0ae1-119">そのメールボックスへのアクセス許可または資格情報への関係は、要因ではありません。電子メールアドレスは、接続先の Exchange Online PowerShell に対してのみを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="f0ae1-120">Microsoft 365 または Microsoft 365 GCC のお客様は、通常、 _Connectionuri_ パラメーターを使用して Exchange Online PowerShell に接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="f0ae1-121">ただし、特定の地域の場所に接続するには、値でを使用できるように、 _Connectionuri_ パラメーターを使用する必要があり `?email=<emailaddress>` ます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-using-multi-factor-authentication-mfa"></a><span data-ttu-id="f0ae1-122">多要素認証 (MFA) を使用して Exchange Online PowerShell で地理的位置に接続する</span><span class="sxs-lookup"><span data-stu-id="f0ae1-122">Connect to a geo location in Exchange Online PowerShell using multi-factor authentication (MFA)</span></span>

1. <span data-ttu-id="f0ae1-123">Windows PowerShell ウィンドウで、次のコマンドを実行して EXO V2 モジュールを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-123">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="f0ae1-124">次の例では、admin@contoso.onmicrosoft.com は管理者アカウントで、ターゲット地域の場所はメールボックス olga@contoso.onmicrosoft.com が存在する場所です。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-124">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

  ```powershell
  Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
  ```

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-without-using-mfa"></a><span data-ttu-id="f0ae1-125">MFA を使用せずに Exchange Online PowerShell で地理的位置に接続する</span><span class="sxs-lookup"><span data-stu-id="f0ae1-125">Connect to a geo location in Exchange Online PowerShell without using MFA</span></span>

1. <span data-ttu-id="f0ae1-126">Windows PowerShell ウィンドウで、次のコマンドを実行して EXO V2 モジュールを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="f0ae1-127">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-127">Run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="f0ae1-128">**[Windows PowerShell 資格情報の要求]** ダイアログ ボックスで、職場または学校のアカウントとパスワードを入力してから **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-128">In the **Windows PowerShell Credential Request** dialog box that appears, type your work or school account and password, and then click **OK**.</span></span>

3. <span data-ttu-id="f0ae1-129">次の例では、ターゲットの地理的位置はメールボックス olga@contoso.onmicrosoft.com が存在する場所です。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-129">In the following example, the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="f0ae1-130">Exchange Online 組織で構成されている使用可能な地域の場所を表示する</span><span class="sxs-lookup"><span data-stu-id="f0ae1-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="f0ae1-131">Microsoft 365 Multi-Geo の構成された地域の場所のリストを参照するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="f0ae1-132">Exchange Online組織の地理上中央位置を表示する</span><span class="sxs-lookup"><span data-stu-id="f0ae1-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="f0ae1-133">テナントの地理上中央位置を表示するには、Exchange Online PowerShellで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="f0ae1-134">メールボックスの地域の場所を検索する</span><span class="sxs-lookup"><span data-stu-id="f0ae1-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="f0ae1-135">Exchange Online PowerShell の **Get-Mailbox** コマンドレットでは、メールボックスの複数地域に関連した以下のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="f0ae1-136">**Database**: データベース名の最初の 3 つの文字は、メールボックスが置かれていることを通知する地域コードに対応します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="f0ae1-137">オンライン アーカイブ メールボックスには、**ArchiveDatabase** が使用される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="f0ae1-138">**MailboxRegion**: 管理者によって設定された地域の場所コード (Azure AD の **PreferredDataLocation** から同期された) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="f0ae1-139">**MailboxRegionLastUpdateTime**: MailboxRegion が (自動または手動で) 最終更新された日時を示します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="f0ae1-140">メールボックスのこれらのプロパティを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="f0ae1-141">たとえば、メール ボックスの chris@contoso.onmicrosoft.com の地理的位置の情報を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="f0ae1-142">コマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="f0ae1-143">データベース名の地理的位置コードが **MailboxRegion** 値と一致しない場合、メールボックスは自動的に再配置キューに配置され、 **MailboxRegion** 値で指定された地理的位置に移動します (Exchange Online は、これらのプロパティ値の不一致を検出します)。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="f0ae1-144">既存のクラウド専用メールボックスを特定の地域の場所に移動する</span><span class="sxs-lookup"><span data-stu-id="f0ae1-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="f0ae1-145">クラウド専用ユーザーとは、AAD Connectを介してテナントと同期していないユーザーです。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="f0ae1-146">このユーザーは、Azure AD で直接作成されました。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="f0ae1-147">クラウド専用ユーザーのメールボックスが格納される地理的な場所を表示または指定するには、Windows PowerShell用Azure ADモジュールの\*\* Get-MsolUser **および** Set-MsolUser \*\*コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="f0ae1-148">ユーザーの **PreferredDataLocation** 値を表示するには、Azure AD PowerShell で次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="f0ae1-149">たとえば、ユーザー michelle@contoso.onmicrosoft.com の **PreferredDataLocation** 値を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="f0ae1-150">クラウド専用ユーザー オブジェクトの **PreferredDataLocation** 値を変更するには、Azure AD PowerShell で次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="f0ae1-151">たとえば、**PreferredDataLocation** 値をユーザー michelle@contoso.onmicrosoft.com の欧州連合 (EUR) 地域に設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="f0ae1-152">前述したように、オンプレミスの Active Directory から同期されたユーザーオブジェクトに対して、この手順を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="f0ae1-153">Active Directory で **PreferredDataLocation** 値を変更し、それを AAD Connect を使用して同期させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="f0ae1-154">詳細については、「[Azure Active Directory Connect 同期: Microsoft 365 リソースの優先されるデータの場所を構成する](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="f0ae1-155">メールボックスを新しい地域の場所に再配置するための所要時間は次のいくつかの要素によって決まります。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="f0ae1-156">メールボックスのサイズと種類。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="f0ae1-157">移行されるメールボックスの数。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="f0ae1-158">リソース移動の可用性。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-158">The availability of move resources.</span></span>

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a><span data-ttu-id="f0ae1-159">訴訟ホールド中の無効のメールボックスを移動する</span><span class="sxs-lookup"><span data-stu-id="f0ae1-159">Move disabled mailboxes that are on Litigation Hold</span></span>

<span data-ttu-id="f0ae1-160">電子情報開示目的で保持されている訴訟ホールド中の無効なメールボックスは、無効状態の **PreferredDataLocation** 値を変更しても移動できません。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-160">Disabled mailboxes on Litigation Hold that are preserved for eDiscovery purposes cannot be moved by changing their **PreferredDataLocation** value in their disabled state.</span></span> <span data-ttu-id="f0ae1-161">訴訟ホールド中の無効なメールボックスを移動するには:</span><span class="sxs-lookup"><span data-stu-id="f0ae1-161">To move a disabled mailbox on litigation hold:</span></span>

1. <span data-ttu-id="f0ae1-162">一時的にライセンスをメールボックスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-162">Temporarily assign a license to the mailbox.</span></span>

2. <span data-ttu-id="f0ae1-163">**PreferredDataLocation** を変更します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-163">Change the **PreferredDataLocation**.</span></span>

3. <span data-ttu-id="f0ae1-164">選択した地域の場所に移動した後に、メールボックスからライセンスを削除して、無効状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-164">Remove the license from the mailbox after it has been moved to the selected geo location to put it back into the disabled state.</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="f0ae1-165">特定の地域の場所に新しいクラウド メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="f0ae1-165">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="f0ae1-166">特定の地域の場所に新しいメールボックスを作成するには、以下の手順のいずれかを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-166">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="f0ae1-167">メールボックスが Exchange Online で作成される*前に*、前のセクションで説明されたように **PreferredDataLocation** を構成します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-167">Configure the **PreferredDataLocation** value as described in the previous section *before* the mailbox is created in Exchange Online.</span></span> <span data-ttu-id="f0ae1-168">たとえば、ライセンスを割り当てる前に、ユーザーに **PreferredDataLocation** 値を構成します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-168">For example, configure the **PreferredDataLocation** value on a user before assigning a license.</span></span>

- <span data-ttu-id="f0ae1-169">**PreferredDataLocation** 値の設定と同時にライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-169">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="f0ae1-170">特定の地域にクラウド専用のライセンスユーザー（AAD Connectと同期していないユーザー）を作成するには、Azure AD PowerShellで次の構文を使用します：</span><span class="sxs-lookup"><span data-stu-id="f0ae1-170">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="f0ae1-171">この例では、次の値を使用して Elizabeth Brunner 用に新しいユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-171">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="f0ae1-172">ユーザー プリンシパル名: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="f0ae1-172">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="f0ae1-173">名: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="f0ae1-173">First name: Elizabeth</span></span>
- <span data-ttu-id="f0ae1-174">姓: Brunner</span><span class="sxs-lookup"><span data-stu-id="f0ae1-174">Last name: Brunner</span></span>
- <span data-ttu-id="f0ae1-175">表示名：Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="f0ae1-175">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="f0ae1-176">パスワード: ランダムに生成され、コマンドの結果に表示される (*パスワード* パラメーターを使用していないため)</span><span class="sxs-lookup"><span data-stu-id="f0ae1-176">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="f0ae1-177">ライセンス：`contoso:ENTERPRISEPREMIUM`（E5）</span><span class="sxs-lookup"><span data-stu-id="f0ae1-177">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="f0ae1-178">場所: オーストラリア (AUS)</span><span class="sxs-lookup"><span data-stu-id="f0ae1-178">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="f0ae1-179">Azure AD PowerShell での新しいユーザー アカウントの作成や LicenseAssignment 値の検索の詳細については、「[PowerShell のユーザー アカウントを作成する](create-user-accounts-with-microsoft-365-powershell.md)」と「[PowerShell でライセンスとサービスを確認する](view-licenses-and-services-with-microsoft-365-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-179">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f0ae1-180">Exchange Online PowerShellを使用してメールボックスを有効にし、メールボックスを\*\* PreferredDataLocation **で指定した地理上の場所に直接作成する必要がある場合は、クラウドサービスに対して** Enable-Mailbox**や**New-Mailbox\*\*などのExchange Onlineコマンドレットを直接使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-180">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="f0ae1-181">オンプレミスのExchange PowerShellで\*\* Enable-RemoteMailbox \*\*コマンドレットを使用すると、メールボックスは地理上の中央位置に作成されます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-181">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="f0ae1-182">既存のオンプレミスのメールボックスを特定の地域の場所にオンボードする</span><span class="sxs-lookup"><span data-stu-id="f0ae1-182">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="f0ae1-183">標準のオンボーディング ツールとプロセスを使用して、オンプレミスの Exchange 組織から Exchange Online にメールボックスを移行できます ([EAC の移行ダッシュボード](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)、および Exchange Online PowerShell の [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) コマンドレットを含む)。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-183">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="f0ae1-184">最初の手順は、オンボードされる各メールボックスにユーザー オブジェクトが存在することを確認し、正しい **PreferredDataLocation** 値が Azure AD で構成されていることを確認することです。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-184">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="f0ae1-185">オンボーディングツールは\*\* PreferredDataLocation \*\*値に従い、メールボックスを指定された地理的位置に直接移行します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-185">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="f0ae1-186">または、Exchange Online PowerShell の [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) コマンドレットを使用してメールボックスを特定の地域に直接オンボードするために次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-186">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="f0ae1-187">オンボードされる各メールボックスにユーザー オブジェクトが存在し、Azure AD で **PreferredDataLocation** が適切な値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-187">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="f0ae1-188">**PreferredDataLocation** の値は、Exchange Online の対応するメール ユーザー オブジェクトの **MailboxRegion** 属性に同期されます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-188">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="f0ae1-189">このトピックの前半の接続手順を使用して、特定の衛星地域に直接接続してください。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-189">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="f0ae1-190">Exchange Online PowerShell で、次のコマンドを実行して、メールボックスの移行を変数で実行するために使用されるオンプレミスの管理者認証情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-190">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="f0ae1-191">Exchange Online PowerShell で、次の例に類似した新しい **New-MoveRequest** を作成します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-191">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="f0ae1-192">オンプレミスのExchangeから現在接続している衛星地域に移行する必要があるメールボックスごとに、手順4を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-192">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="f0ae1-193">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span><span class="sxs-lookup"><span data-stu-id="f0ae1-193">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="f0ae1-194">複数地域レポート</span><span class="sxs-lookup"><span data-stu-id="f0ae1-194">Multi-geo reporting</span></span>

<span data-ttu-id="f0ae1-195">Microsoft 365 管理センターの**複数地域利用状況レポート**では、地域の場所ごとのユーザー数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-195">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="f0ae1-196">レポートには、当月のユーザー分布が表示され、過去 6 か月間の履歴データが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f0ae1-196">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0ae1-197">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0ae1-197">See also</span></span>

[<span data-ttu-id="f0ae1-198">Windows PowerShell で Microsoft 365 と Exchange Online を管理する</span><span class="sxs-lookup"><span data-stu-id="f0ae1-198">Managing Microsoft 365 and Exchange Online with Windows PowerShell</span></span>](https://support.office.com//article/06a743bb-ceb6-49a9-a61d-db4ffdf54fa6)
