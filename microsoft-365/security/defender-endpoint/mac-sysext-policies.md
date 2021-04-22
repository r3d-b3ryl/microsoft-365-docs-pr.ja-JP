---
title: macOS Catalina および macOS の新しいバージョンの新しい構成プロファイル
description: このトピックでは、macOS Catalina および macOS の新しいバージョンのカーネル拡張機能に代わるシステム拡張機能を利用するために行う必要がある変更について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, kernel, system, extensions, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 28a332cec68521741bdda62aeecd25440552344a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932741"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a><span data-ttu-id="921bb-104">macOS Catalina および macOS の新しいバージョンの新しい構成プロファイル</span><span class="sxs-lookup"><span data-stu-id="921bb-104">New configuration profiles for macOS Catalina and newer versions of macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="921bb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="921bb-105">**Applies to:**</span></span>
- [<span data-ttu-id="921bb-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="921bb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="921bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="921bb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="921bb-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="921bb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="921bb-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="921bb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="921bb-110">macOS の進化に合わせ、カーネル拡張機能ではなくシステム拡張機能を活用する macOS 更新プログラムの Microsoft Defender for Endpoint を準備しています。</span><span class="sxs-lookup"><span data-stu-id="921bb-110">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on macOS update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="921bb-111">この更新プログラムは、macOS Catalina (10.15.4) 以降のバージョンの macOS にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="921bb-111">This update will only be applicable to macOS Catalina (10.15.4) and newer versions of macOS.</span></span>

<span data-ttu-id="921bb-112">管理環境 (JAMF、Intune、または別の MDM ソリューションを介して) macOS に Microsoft Defender for Endpoint を展開している場合は、新しい構成プロファイルを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="921bb-112">If you have deployed Microsoft Defender for Endpoint on macOS in a managed environment (through JAMF, Intune, or another MDM solution), you must deploy new configuration profiles.</span></span> <span data-ttu-id="921bb-113">これらの手順を実行しない場合、ユーザーは、これらの新しいコンポーネントを実行するための承認プロンプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="921bb-113">Failure to do these steps will result in users getting approval prompts to run these new components.</span></span>

## <a name="jamf"></a><span data-ttu-id="921bb-114">JAMF</span><span class="sxs-lookup"><span data-stu-id="921bb-114">JAMF</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="921bb-115">システム拡張機能ポリシー</span><span class="sxs-lookup"><span data-stu-id="921bb-115">System Extensions Policy</span></span>

<span data-ttu-id="921bb-116">システム拡張機能を承認するには、次のペイロードを作成します。</span><span class="sxs-lookup"><span data-stu-id="921bb-116">To approve the system extensions, create the following payload:</span></span>

1. <span data-ttu-id="921bb-117">[**コンピューター] >構成プロファイルで、[\*\*\*\*システム拡張機能>オプション] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="921bb-117">In **Computers > Configuration Profiles** select **Options > System Extensions**.</span></span>
2. <span data-ttu-id="921bb-118">[ **システム拡張の種類] ドロップダウン リスト** から [ **許可されたシステム拡張機能** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="921bb-118">Select **Allowed System Extensions** from the **System Extension Types** drop-down list.</span></span>
3. <span data-ttu-id="921bb-119">チーム **ID には UBF8T346G9** を使用します。</span><span class="sxs-lookup"><span data-stu-id="921bb-119">Use **UBF8T346G9** for Team Id.</span></span>
4. <span data-ttu-id="921bb-120">次のバンドル識別子を [許可されたシステム拡張機能] リスト **に追加** します。</span><span class="sxs-lookup"><span data-stu-id="921bb-120">Add the following bundle identifiers to the **Allowed System Extensions** list:</span></span>

    - <span data-ttu-id="921bb-121">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="921bb-121">**com.microsoft.wdav.epsext**</span></span>
    - <span data-ttu-id="921bb-122">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="921bb-122">**com.microsoft.wdav.netext**</span></span>

    ![承認済みのシステム拡張機能のスクリーンショット](images/mac-approved-system-extensions.png)

### <a name="privacy-preferences-policy-control"></a><span data-ttu-id="921bb-124">プライバシー設定ポリシー制御</span><span class="sxs-lookup"><span data-stu-id="921bb-124">Privacy Preferences Policy Control</span></span>

<span data-ttu-id="921bb-125">次の JAMF ペイロードを追加して、Microsoft Defender for Endpoint Security Extension にフル ディスク アクセスを付与します。</span><span class="sxs-lookup"><span data-stu-id="921bb-125">Add the following JAMF payload to grant Full Disk Access to the Microsoft Defender for Endpoint Endpoint Security Extension.</span></span> <span data-ttu-id="921bb-126">このポリシーは、デバイスで拡張機能を実行する前提条件です。</span><span class="sxs-lookup"><span data-stu-id="921bb-126">This policy is a pre-requisite for running the extension on your device.</span></span>

1. <span data-ttu-id="921bb-127">[オプション **]**  >  **[プライバシー設定] ポリシーコントロールを選択します**。</span><span class="sxs-lookup"><span data-stu-id="921bb-127">Select **Options** > **Privacy Preferences Policy Control**.</span></span>
2. <span data-ttu-id="921bb-128">識別子 `com.microsoft.wdav.epsext` として、 **バンドル** `Bundle ID` の **種類として使用します**。</span><span class="sxs-lookup"><span data-stu-id="921bb-128">Use `com.microsoft.wdav.epsext` as the **Identifier** and `Bundle ID` as **Bundle type**.</span></span>
3. <span data-ttu-id="921bb-129">コード要件をに設定する `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="921bb-129">Set Code Requirement to `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
4. <span data-ttu-id="921bb-130">アプリ **またはサービスを** **SystemPolicyAllFiles** に設定し、[許可] に **アクセスします**。</span><span class="sxs-lookup"><span data-stu-id="921bb-130">Set **App or service** to **SystemPolicyAllFiles** and access to **Allow**.</span></span>

    ![プライバシー設定ポリシー制御](images/mac-system-extension-privacy.png)

### <a name="network-extension-policy"></a><span data-ttu-id="921bb-132">ネットワーク拡張ポリシー</span><span class="sxs-lookup"><span data-stu-id="921bb-132">Network Extension Policy</span></span>

<span data-ttu-id="921bb-133">エンドポイント検出および応答機能の一環として、macOS 上の Microsoft Defender for Endpoint はソケット トラフィックを検査し、この情報を Microsoft Defender セキュリティ センター ポータルに報告します。</span><span class="sxs-lookup"><span data-stu-id="921bb-133">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="921bb-134">次のポリシーでは、ネットワーク拡張機能でこの機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="921bb-134">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="921bb-135">JAMF には、コンテンツ フィルター ポリシーの組み込みのサポートが用意されていません。これは、macOS 上の Microsoft Defender for Endpoint がデバイスにインストールするネットワーク拡張機能を有効にするための前提条件です。</span><span class="sxs-lookup"><span data-stu-id="921bb-135">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint on macOS installs on the device.</span></span> <span data-ttu-id="921bb-136">さらに、JAMF は展開するポリシーの内容を変更する場合があります。</span><span class="sxs-lookup"><span data-stu-id="921bb-136">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="921bb-137">そのため、次の手順では、構成プロファイルに署名する回避策を提供します。</span><span class="sxs-lookup"><span data-stu-id="921bb-137">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="921bb-138">テキスト エディターを使用して、次のコンテンツを `com.microsoft.network-extension.mobileconfig` デバイスに保存します。</span><span class="sxs-lookup"><span data-stu-id="921bb-138">Save the following content to your device as `com.microsoft.network-extension.mobileconfig` using a text editor:</span></span>

    ```xml
    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1">
        <dict>
            <key>PayloadUUID</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadType</key>
            <string>Configuration</string>
            <key>PayloadOrganization</key>
            <string>Microsoft Corporation</string>
            <key>PayloadIdentifier</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft Defender ATP Network Extension</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>PayloadRemovalDisallowed</key>
            <true/>
            <key>PayloadScope</key>
            <string>System</string>
            <key>PayloadContent</key>
            <array>
                <dict>
                    <key>PayloadUUID</key>
                    <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                    <key>PayloadType</key>
                    <string>com.apple.webcontent-filter</string>
                    <key>PayloadOrganization</key>
                    <string>Microsoft Corporation</string>
                    <key>PayloadIdentifier</key>
                    <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                    <key>PayloadDisplayName</key>
                    <string>Approved Network Extension</string>
                    <key>PayloadDescription</key>
                    <string/>
                    <key>PayloadVersion</key>
                    <integer>1</integer>
                    <key>PayloadEnabled</key>
                    <true/>
                    <key>FilterType</key>
                    <string>Plugin</string>
                    <key>UserDefinedName</key>
                    <string>Microsoft Defender ATP Network Extension</string>
                    <key>PluginBundleID</key>
                    <string>com.microsoft.wdav</string>
                    <key>FilterSockets</key>
                    <true/>
                    <key>FilterDataProviderBundleIdentifier</key>
                    <string>com.microsoft.wdav.netext</string>
                    <key>FilterDataProviderDesignatedRequirement</key>
                    <string>identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                </dict>
            </array>
        </dict>
    </plist>
    ```

2. <span data-ttu-id="921bb-139">ターミナルでユーティリティを実行して、上記のファイルが正 `plutil` しくコピーされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="921bb-139">Verify that the above file was copied correctly by running the `plutil` utility in the Terminal:</span></span>

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    <span data-ttu-id="921bb-140">たとえば、ファイルが Documents に保存されている場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="921bb-140">For example, if the file was stored in Documents:</span></span>

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```
    
    <span data-ttu-id="921bb-141">コマンドが出力されるのを確認します `OK` 。</span><span class="sxs-lookup"><span data-stu-id="921bb-141">Verify that the command outputs `OK`.</span></span>
        
    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```
    
3. <span data-ttu-id="921bb-142">JAMF の組 [み込](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) みの証明機関を使用して署名証明書を作成するには、このページの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="921bb-142">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority.</span></span>

4. <span data-ttu-id="921bb-143">証明書を作成してデバイスにインストールしたら、ターミナルから次のコマンドを実行してファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="921bb-143">After the certificate is created and installed to your device, run the following command from the Terminal to sign the file:</span></span>

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```
    
    <span data-ttu-id="921bb-144">たとえば、証明書名が **SigningCertificate** で、署名されたファイルが Documents に格納される場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="921bb-144">For example, if the certificate name is **SigningCertificate** and the signed file is going to be stored in Documents:</span></span>
    
    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```
    
5. <span data-ttu-id="921bb-145">JAMF ポータルから [構成プロファイル] に移動 **し、[** アップロード] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="921bb-145">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> <span data-ttu-id="921bb-146">ファイル `com.microsoft.network-extension.signed.mobileconfig` の入力を求めるメッセージが表示されたら選択します。</span><span class="sxs-lookup"><span data-stu-id="921bb-146">Select `com.microsoft.network-extension.signed.mobileconfig` when prompted for the file.</span></span>

## <a name="intune"></a><span data-ttu-id="921bb-147">Intune</span><span class="sxs-lookup"><span data-stu-id="921bb-147">Intune</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="921bb-148">システム拡張機能ポリシー</span><span class="sxs-lookup"><span data-stu-id="921bb-148">System Extensions Policy</span></span>

<span data-ttu-id="921bb-149">システム拡張機能を承認するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="921bb-149">To approve the system extensions:</span></span>

1. <span data-ttu-id="921bb-150">Intune で、[デバイス構成の **管理**  >  **] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="921bb-150">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="921bb-151">[プロファイル **の**  >  **管理] [プロファイルの**  >  **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="921bb-151">Select **Manage** > **Profiles** > **Create Profile**.</span></span>
2. <span data-ttu-id="921bb-152">プロファイルの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="921bb-152">Choose a name for the profile.</span></span> <span data-ttu-id="921bb-153">**Platform=macOS を Profile** **type=Extensions に変更します**。</span><span class="sxs-lookup"><span data-stu-id="921bb-153">Change **Platform=macOS** to **Profile type=Extensions**.</span></span> <span data-ttu-id="921bb-154">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="921bb-154">Select **Create**.</span></span>
3. <span data-ttu-id="921bb-155">タブで `Basics` 、この新しいプロファイルに名前を付きます。</span><span class="sxs-lookup"><span data-stu-id="921bb-155">In the `Basics` tab, give a name to this new profile.</span></span>
4. <span data-ttu-id="921bb-156">タブで `Configuration settings` 、セクションに次のエントリを追加 `Allowed system extensions` します。</span><span class="sxs-lookup"><span data-stu-id="921bb-156">In the `Configuration settings` tab, add the following entries in the `Allowed system extensions` section:</span></span>

    <span data-ttu-id="921bb-157">バンドル識別子</span><span class="sxs-lookup"><span data-stu-id="921bb-157">Bundle identifier</span></span>         | <span data-ttu-id="921bb-158">チーム識別子</span><span class="sxs-lookup"><span data-stu-id="921bb-158">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="921bb-159">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="921bb-159">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="921bb-160">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="921bb-160">UBF8T346G9</span></span>
    <span data-ttu-id="921bb-161">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="921bb-161">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="921bb-162">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="921bb-162">UBF8T346G9</span></span>

    ![システム構成プロファイルのスクリーンショット](images/mac-system-extension-intune2.png)

5. <span data-ttu-id="921bb-164">タブで `Assignments` 、このプロファイルを [すべてのユーザー] に割り当& **すべてのデバイスに割り当てる必要があります**。</span><span class="sxs-lookup"><span data-stu-id="921bb-164">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="921bb-165">この構成プロファイルを確認して作成します。</span><span class="sxs-lookup"><span data-stu-id="921bb-165">Review and create this configuration profile.</span></span>

### <a name="create-and-deploy-the-custom-configuration-profile"></a><span data-ttu-id="921bb-166">カスタム構成プロファイルの作成と展開</span><span class="sxs-lookup"><span data-stu-id="921bb-166">Create and deploy the Custom Configuration Profile</span></span>

<span data-ttu-id="921bb-167">次の構成プロファイルは、ネットワーク拡張機能を有効にし、エンドポイント セキュリティ システム拡張機能へのフル ディスク アクセスを付与します。</span><span class="sxs-lookup"><span data-stu-id="921bb-167">The following configuration profile enables the network extension and grants Full Disk Access to the Endpoint Security system extension.</span></span> 

<span data-ttu-id="921bb-168">次のコンテンツを次の名前の **ファイルに保存** sysext.xml。</span><span class="sxs-lookup"><span data-stu-id="921bb-168">Save the following content to a file named **sysext.xml**:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft Corporation</string>
        <key>PayloadIdentifier</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender ATP System Extensions</string>
        <key>PayloadDescription</key>
        <string/>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                <key>PayloadType</key>
                <string>com.apple.webcontent-filter</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                <key>PayloadDisplayName</key>
                <string>Approved Network Extension</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>FilterType</key>
                <string>Plugin</string>
                <key>UserDefinedName</key>
                <string>Microsoft Defender ATP Network Extension</string>
                <key>PluginBundleID</key>
                <string>com.microsoft.wdav</string>
                <key>FilterSockets</key>
                <true/>
                <key>FilterDataProviderBundleIdentifier</key>
                <string>com.microsoft.wdav.netext</string>
                <key>FilterDataProviderDesignatedRequirement</key>
                <string>identifier &quot;com.microsoft.wdav.netext&quot; and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
            </dict>
            <dict>
                <key>PayloadUUID</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadType</key>
                <string>com.apple.TCC.configuration-profile-policy</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadDisplayName</key>
                <string>Privacy Preferences Policy Control</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>Services</key>
                <dict>
                    <key>SystemPolicyAllFiles</key>
                    <array>
                        <dict>
                            <key>Identifier</key>
                            <string>com.microsoft.wdav.epsext</string>
                            <key>CodeRequirement</key>
                            <string>identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                            <key>IdentifierType</key>
                            <string>bundleID</string>
                            <key>StaticCode</key>
                            <integer>0</integer>
                            <key>Allowed</key>
                            <integer>1</integer>
                        </dict>
                    </array>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="921bb-169">上記のファイルが正しくコピーされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="921bb-169">Verify that the above file was copied correctly.</span></span> <span data-ttu-id="921bb-170">ターミナルから、次のコマンドを実行し、出力を確認します `OK` 。</span><span class="sxs-lookup"><span data-stu-id="921bb-170">From the Terminal, run the following command and verify that it outputs `OK`:</span></span>

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

<span data-ttu-id="921bb-171">このカスタム構成プロファイルを展開するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="921bb-171">To deploy this custom configuration profile:</span></span>

1.  <span data-ttu-id="921bb-172">Intune で、[デバイス構成の **管理**  >  **] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="921bb-172">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="921bb-173">[プロファイル **の**  >  **管理] [プロファイルの**  >  **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="921bb-173">Select **Manage** > **Profiles** > **Create profile**.</span></span>
2. <span data-ttu-id="921bb-174">プロファイルの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="921bb-174">Choose a name for the profile.</span></span> <span data-ttu-id="921bb-175">**Platform=macOS と** **Profile type=Custom を変更します**。</span><span class="sxs-lookup"><span data-stu-id="921bb-175">Change **Platform=macOS** and **Profile type=Custom**.</span></span> <span data-ttu-id="921bb-176">[構成 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="921bb-176">Select **Configure**.</span></span>
3.  <span data-ttu-id="921bb-177">構成プロファイルを開 **き、sysext.xml。**</span><span class="sxs-lookup"><span data-stu-id="921bb-177">Open the configuration profile and upload **sysext.xml**.</span></span> <span data-ttu-id="921bb-178">このファイルは、前の手順で作成されました。</span><span class="sxs-lookup"><span data-stu-id="921bb-178">This file was created in the preceding step.</span></span>
4.  <span data-ttu-id="921bb-179">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="921bb-179">Select **OK**.</span></span>

    ![Intune のスクリーンショットのシステム拡張機能](images/mac-system-extension-intune.png)

5. <span data-ttu-id="921bb-181">タブで `Assignments` 、このプロファイルを [すべてのユーザー] に割り当& **すべてのデバイスに割り当てる必要があります**。</span><span class="sxs-lookup"><span data-stu-id="921bb-181">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="921bb-182">この構成プロファイルを確認して作成します。</span><span class="sxs-lookup"><span data-stu-id="921bb-182">Review and create this configuration profile.</span></span>
