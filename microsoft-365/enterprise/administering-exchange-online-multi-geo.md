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
ms.openlocfilehash: 63eb1957611fd57e216012435188a6ddd1b232d3
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552009"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="0b309-103">複数地域環境での Exchange Online メールボックスの管理</span><span class="sxs-lookup"><span data-stu-id="0b309-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="0b309-104">Microsoft 365 環境で複数の geo プロパティを表示および構成するには、Exchange Online PowerShell が必要です。</span><span class="sxs-lookup"><span data-stu-id="0b309-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="0b309-105">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b309-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="0b309-106">ユーザー オブジェクトの **PreferredDataLocation** プロパティを参照するには、v1.x に [Microsoft Azure Active Directory PowerShell モジュール](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="0b309-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="0b309-107">AAD Connect 経由で AAD に同期されたユーザー オブジェクトでは、**PreferredDataLocation** 値を AAD PowerShell 経由で直接変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b309-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="0b309-108">クラウド専用ユーザー オブジェクトは、AAD PowerShell 経由で変更できます。</span><span class="sxs-lookup"><span data-stu-id="0b309-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="0b309-109">Azure AD PowerShell に接続するには、「[PowerShell への接続](connect-to-microsoft-365-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b309-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="0b309-110">Exchange Online PowerShell を使用して、地域の場所に直接接続する</span><span class="sxs-lookup"><span data-stu-id="0b309-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="0b309-111">通常、Exchange Online PowerShellは地理上の中央位置に接続します。</span><span class="sxs-lookup"><span data-stu-id="0b309-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="0b309-112">しかし、衛星の地理的位置に直接接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b309-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="0b309-113">パフォーマンスが向上するため、その場所にいるユーザーのみを管理している場合は、衛星地域に直接接続することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b309-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="0b309-114">EXO V2 モジュールをインストールして使用するための要件は、「[EXO V2 モジュールをインストールして維持する](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="0b309-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="0b309-115">Exchange Online の PowerShell を特定の地域の場所に接続するために、 *Connectionuri* パラメーターは通常の接続手順とは異なります。</span><span class="sxs-lookup"><span data-stu-id="0b309-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="0b309-116">残りのコマンドと値は同じです。</span><span class="sxs-lookup"><span data-stu-id="0b309-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="0b309-117">具体的には、 `?email=<emailaddress>` _connectionuri_ 値の末尾に値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b309-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="0b309-118">`<emailaddress>` は、対象と **なる** 地域の場所にあるメールボックスの電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="0b309-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="0b309-119">そのメールボックスへのアクセス許可または資格情報への関係は、要因ではありません。電子メールアドレスは、接続先の Exchange Online PowerShell に対してのみを指定します。</span><span class="sxs-lookup"><span data-stu-id="0b309-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="0b309-120">Microsoft 365 または Microsoft 365 GCC のお客様は、通常、 _Connectionuri_ パラメーターを使用して Exchange Online PowerShell に接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0b309-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="0b309-121">ただし、特定の地域の場所に接続するには、値でを使用できるように、 _Connectionuri_ パラメーターを使用する必要があり `?email=<emailaddress>` ます。</span><span class="sxs-lookup"><span data-stu-id="0b309-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a><span data-ttu-id="0b309-122">Exchange Online PowerShell で地域の場所に接続する</span><span class="sxs-lookup"><span data-stu-id="0b309-122">Connect to a geo location in Exchange Online PowerShell</span></span>

<span data-ttu-id="0b309-123">次の接続手順は、多要素認証 (MFA) 用に構成されていない、または構成されていないアカウントに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="0b309-123">The following connection instructions work for accounts that are or aren't configured for multi-factor authentication (MFA).</span></span>

1. <span data-ttu-id="0b309-124">Windows PowerShell ウィンドウで、次のコマンドを実行して EXO V2 モジュールを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="0b309-124">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="0b309-125">次の例では、admin@contoso.onmicrosoft.com は管理者アカウントで、ターゲット地域の場所はメールボックス olga@contoso.onmicrosoft.com が存在する場所です。</span><span class="sxs-lookup"><span data-stu-id="0b309-125">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. <span data-ttu-id="0b309-126">表示されるプロンプトに、admin@contoso.onmicrosoft.com のパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="0b309-126">Enter the password for the admin@contoso.onmicrosoft.com in the prompt that appears.</span></span> <span data-ttu-id="0b309-127">アカウントが MFA に対して構成されている場合は、セキュリティコードも入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b309-127">If the account is configured for MFA, you also need to enter the security code.</span></span>

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="0b309-128">Exchange Online 組織で構成されている使用可能な地域の場所を表示する</span><span class="sxs-lookup"><span data-stu-id="0b309-128">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="0b309-129">Microsoft 365 Multi-Geo の構成された地域の場所のリストを参照するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b309-129">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="0b309-130">Exchange Online組織の地理上中央位置を表示する</span><span class="sxs-lookup"><span data-stu-id="0b309-130">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="0b309-131">テナントの地理上中央位置を表示するには、Exchange Online PowerShellで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b309-131">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="0b309-132">メールボックスの地域の場所を検索する</span><span class="sxs-lookup"><span data-stu-id="0b309-132">Find the geo location of a mailbox</span></span>

<span data-ttu-id="0b309-133">Exchange Online PowerShell の **Get-Mailbox** コマンドレットでは、メールボックスの複数地域に関連した以下のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b309-133">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="0b309-134">**Database**: データベース名の最初の 3 つの文字は、メールボックスが置かれていることを通知する地域コードに対応します。</span><span class="sxs-lookup"><span data-stu-id="0b309-134">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="0b309-135">オンライン アーカイブ メールボックスには、**ArchiveDatabase** が使用される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b309-135">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="0b309-136">**MailboxRegion**: 管理者によって設定された地域の場所コード (Azure AD の **PreferredDataLocation** から同期された) を指定します。</span><span class="sxs-lookup"><span data-stu-id="0b309-136">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="0b309-137">**MailboxRegionLastUpdateTime**: MailboxRegion が (自動または手動で) 最終更新された日時を示します。</span><span class="sxs-lookup"><span data-stu-id="0b309-137">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="0b309-138">メールボックスのこれらのプロパティを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b309-138">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="0b309-139">たとえば、メール ボックスの chris@contoso.onmicrosoft.com の地理的位置の情報を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b309-139">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="0b309-140">コマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0b309-140">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="0b309-141">データベース名の地理的位置コードが **MailboxRegion** 値と一致しない場合、メールボックスは自動的に再配置キューに配置され、 **MailboxRegion** 値で指定された地理的位置に移動します (Exchange Online は、これらのプロパティ値の不一致を検出します)。</span><span class="sxs-lookup"><span data-stu-id="0b309-141">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="0b309-142">既存のクラウド専用メールボックスを特定の地域の場所に移動する</span><span class="sxs-lookup"><span data-stu-id="0b309-142">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="0b309-143">クラウド専用ユーザーとは、AAD Connectを介してテナントと同期していないユーザーです。</span><span class="sxs-lookup"><span data-stu-id="0b309-143">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="0b309-144">このユーザーは、Azure AD で直接作成されました。</span><span class="sxs-lookup"><span data-stu-id="0b309-144">This user was created directly in Azure AD.</span></span> <span data-ttu-id="0b309-145">クラウド専用ユーザーのメールボックスが格納される地理的な場所を表示または指定するには、Windows PowerShell用Azure ADモジュールの **Get-MsolUser** および **Set-MsolUser** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b309-145">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="0b309-146">ユーザーの **PreferredDataLocation** 値を表示するには、Azure AD PowerShell で次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b309-146">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="0b309-147">たとえば、ユーザー michelle@contoso.onmicrosoft.com の **PreferredDataLocation** 値を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b309-147">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="0b309-148">クラウド専用ユーザー オブジェクトの **PreferredDataLocation** 値を変更するには、Azure AD PowerShell で次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b309-148">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="0b309-149">たとえば、**PreferredDataLocation** 値をユーザー michelle@contoso.onmicrosoft.com の欧州連合 (EUR) 地域に設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b309-149">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="0b309-150">前述したように、オンプレミスの Active Directory から同期されたユーザーオブジェクトに対して、この手順を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b309-150">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="0b309-151">Active Directory で **PreferredDataLocation** 値を変更し、それを AAD Connect を使用して同期させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b309-151">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="0b309-152">詳細については、「[Azure Active Directory Connect 同期: Microsoft 365 リソースの優先されるデータの場所を構成する](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b309-152">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="0b309-153">メールボックスを新しい地域の場所に再配置するための所要時間は次のいくつかの要素によって決まります。</span><span class="sxs-lookup"><span data-stu-id="0b309-153">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="0b309-154">メールボックスのサイズと種類。</span><span class="sxs-lookup"><span data-stu-id="0b309-154">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="0b309-155">移行されるメールボックスの数。</span><span class="sxs-lookup"><span data-stu-id="0b309-155">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="0b309-156">リソース移動の可用性。</span><span class="sxs-lookup"><span data-stu-id="0b309-156">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="0b309-157">非アクティブなメールボックスを特定の地域に移動する</span><span class="sxs-lookup"><span data-stu-id="0b309-157">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="0b309-158">**PreferredDataLocation** 値を変更することで、コンプライアンスの目的で保持されている非アクティブなメールボックス (訴訟ホールドのメールボックスなど) を移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b309-158">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="0b309-159">非アクティブなメールボックスを別の geo に移動するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0b309-159">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="0b309-160">非アクティブなメールボックスを回復します。</span><span class="sxs-lookup"><span data-stu-id="0b309-160">Recover the inactive mailbox.</span></span> <span data-ttu-id="0b309-161">手順については、「 [非アクティブなメールボックスを回復する](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b309-161">For instructions, see [Recover an inactive mailbox](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).</span></span>

2. <span data-ttu-id="0b309-162">管理フォルダーアシスタントが、 \<MailboxIdentity\> メールボックスの名前、エイリアス、アカウント、または電子メールアドレスに置き換え、 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)で次のコマンドを実行して、回復されたメールボックスを処理できないようにします。</span><span class="sxs-lookup"><span data-stu-id="0b309-162">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="0b309-163">回復されたメールボックスに **Exchange Online プラン 2** ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0b309-163">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="0b309-164">この手順は、メールボックスを訴訟ホールドの対象に戻すために必要です。</span><span class="sxs-lookup"><span data-stu-id="0b309-164">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="0b309-165">手順については、「 [ユーザーへのライセンスの割り当て](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b309-165">For instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

4. <span data-ttu-id="0b309-166">前のセクションで説明したように、メールボックスの **PreferredDataLocation** 値を構成します。</span><span class="sxs-lookup"><span data-stu-id="0b309-166">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="0b309-167">メールボックスが新しい地域の場所に移動されたことを確認した後、回復されたメールボックスを訴訟ホールドの対象に戻します。</span><span class="sxs-lookup"><span data-stu-id="0b309-167">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="0b309-168">手順については、「 [メールボックスを訴訟ホールドの対象にする](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b309-168">For instructions, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="0b309-169">訴訟ホールドが有効になっていることを確認した後、 \<MailboxIdentity\> メールボックスの名前、エイリアス、アカウント、または電子メールアドレスで置き換えて、 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)で次のコマンドを実行することによって、管理フォルダーアシスタントがメールボックスを再度処理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0b309-169">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="0b309-170">メールボックスに関連付けられているユーザーアカウントを削除して、メールボックスを再度非アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="0b309-170">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="0b309-171">手順については、「 [組織からユーザーを削除する](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b309-171">For instructions, see [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span></span> <span data-ttu-id="0b309-172">この手順では、他の用途に対して Exchange Online プラン2ライセンスも解放されます。</span><span class="sxs-lookup"><span data-stu-id="0b309-172">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="0b309-173">**注**: 非アクティブなメールボックスを別の地域の場所に移動すると、コンテンツ検索の結果に影響を与えたり、以前の地理的位置からメールボックスを検索したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b309-173">**Note**: When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="0b309-174">詳細については、「 [複数地域環境でのコンテンツの検索とエクスポート](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b309-174">For more information, see [Searching and exporting content in Multi-Geo environments](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="0b309-175">特定の地域の場所に新しいクラウド メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="0b309-175">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="0b309-176">特定の地域の場所に新しいメールボックスを作成するには、以下の手順のいずれかを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b309-176">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="0b309-177">Exchange Online でメールボックスを作成する *前* に、前の「[既存のクラウドのみのメールボックスを特定の地域の場所に移動](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location)する」の説明に従って、 **PreferredDataLocation** の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="0b309-177">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="0b309-178">たとえば、ライセンスを割り当てる前にユーザーの **PreferredDataLocation** 値を構成します。</span><span class="sxs-lookup"><span data-stu-id="0b309-178">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="0b309-179">**PreferredDataLocation** 値の設定と同時にライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0b309-179">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="0b309-180">特定の地域にクラウド専用のライセンスユーザー（AAD Connectと同期していないユーザー）を作成するには、Azure AD PowerShellで次の構文を使用します：</span><span class="sxs-lookup"><span data-stu-id="0b309-180">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="0b309-181">この例では、次の値を使用して Elizabeth Brunner 用に新しいユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="0b309-181">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="0b309-182">ユーザー プリンシパル名: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0b309-182">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="0b309-183">名: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="0b309-183">First name: Elizabeth</span></span>
- <span data-ttu-id="0b309-184">姓: Brunner</span><span class="sxs-lookup"><span data-stu-id="0b309-184">Last name: Brunner</span></span>
- <span data-ttu-id="0b309-185">表示名：Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="0b309-185">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="0b309-186">パスワード: ランダムに生成され、コマンドの結果に表示される (*パスワード* パラメーターを使用していないため)</span><span class="sxs-lookup"><span data-stu-id="0b309-186">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="0b309-187">ライセンス：`contoso:ENTERPRISEPREMIUM`（E5）</span><span class="sxs-lookup"><span data-stu-id="0b309-187">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="0b309-188">場所: オーストラリア (AUS)</span><span class="sxs-lookup"><span data-stu-id="0b309-188">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="0b309-189">Azure AD PowerShell での新しいユーザー アカウントの作成や LicenseAssignment 値の検索の詳細については、「[PowerShell のユーザー アカウントを作成する](create-user-accounts-with-microsoft-365-powershell.md)」と「[PowerShell でライセンスとサービスを確認する](view-licenses-and-services-with-microsoft-365-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b309-189">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0b309-190">Exchange Online PowerShellを使用してメールボックスを有効にし、メールボックスを **PreferredDataLocation** で指定した地理上の場所に直接作成する必要がある場合は、クラウドサービスに対して **Enable-Mailbox** や **New-Mailbox** などのExchange Onlineコマンドレットを直接使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b309-190">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="0b309-191">オンプレミスのExchange PowerShellで **Enable-RemoteMailbox** コマンドレットを使用すると、メールボックスは地理上の中央位置に作成されます。</span><span class="sxs-lookup"><span data-stu-id="0b309-191">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="0b309-192">既存のオンプレミスのメールボックスを特定の地域の場所にオンボードする</span><span class="sxs-lookup"><span data-stu-id="0b309-192">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="0b309-193">標準のオンボーディング ツールとプロセスを使用して、オンプレミスの Exchange 組織から Exchange Online にメールボックスを移行できます ([EAC の移行ダッシュボード](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)、および Exchange Online PowerShell の [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) コマンドレットを含む)。</span><span class="sxs-lookup"><span data-stu-id="0b309-193">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="0b309-194">最初の手順は、オンボードされる各メールボックスにユーザー オブジェクトが存在することを確認し、正しい **PreferredDataLocation** 値が Azure AD で構成されていることを確認することです。</span><span class="sxs-lookup"><span data-stu-id="0b309-194">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="0b309-195">オンボーディングツールは **PreferredDataLocation** 値に従い、メールボックスを指定された地理的位置に直接移行します。</span><span class="sxs-lookup"><span data-stu-id="0b309-195">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="0b309-196">または、Exchange Online PowerShell の [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) コマンドレットを使用してメールボックスを特定の地域に直接オンボードするために次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b309-196">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="0b309-197">オンボードされる各メールボックスにユーザー オブジェクトが存在し、Azure AD で **PreferredDataLocation** が適切な値に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b309-197">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="0b309-198">**PreferredDataLocation** の値は、Exchange Online の対応するメール ユーザー オブジェクトの **MailboxRegion** 属性に同期されます。</span><span class="sxs-lookup"><span data-stu-id="0b309-198">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="0b309-199">このトピックの前半の接続手順を使用して、特定の衛星地域に直接接続してください。</span><span class="sxs-lookup"><span data-stu-id="0b309-199">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="0b309-200">Exchange Online PowerShell で、次のコマンドを実行して、メールボックスの移行を変数で実行するために使用されるオンプレミスの管理者認証情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="0b309-200">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="0b309-201">Exchange Online PowerShell で、次の例に類似した新しい **New-MoveRequest** を作成します。</span><span class="sxs-lookup"><span data-stu-id="0b309-201">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="0b309-202">オンプレミスのExchangeから現在接続している衛星地域に移行する必要があるメールボックスごとに、手順4を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0b309-202">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="0b309-203">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span><span class="sxs-lookup"><span data-stu-id="0b309-203">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="0b309-204">複数地域レポート</span><span class="sxs-lookup"><span data-stu-id="0b309-204">Multi-geo reporting</span></span>

<span data-ttu-id="0b309-205">Microsoft 365 管理センターの **複数地域利用状況レポート** では、地域の場所ごとのユーザー数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b309-205">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="0b309-206">レポートには、当月のユーザー分布が表示され、過去 6 か月間の履歴データが提供されます。</span><span class="sxs-lookup"><span data-stu-id="0b309-206">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b309-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b309-207">See also</span></span>

[<span data-ttu-id="0b309-208">PowerShell で Microsoft 365を管理する</span><span class="sxs-lookup"><span data-stu-id="0b309-208">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
