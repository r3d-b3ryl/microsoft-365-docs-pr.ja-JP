---
title: Linux 用 Microsoft Defender ATP の除外を構成および検証する
description: Linux 用 Microsoft Defender ATP の除外を指定して検証します。 除外は、ファイル、フォルダー、およびプロセスに対して設定できます。
keywords: microsoft、Defender、atp、Linux、除外、スキャン、ウイルス対策
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f5e9c237f53351df0249f0a12d08b8ba61572f7e
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587085"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="96922-105">Microsoft Defender for Endpoint for Linux の除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="96922-105">Configure and validate exclusions for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="96922-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="96922-106">**Applies to:**</span></span>
- [<span data-ttu-id="96922-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="96922-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="96922-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96922-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="96922-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="96922-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="96922-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="96922-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="96922-111">この記事では、オンデマンド スキャンに適用される除外を定義する方法、およびリアルタイムの保護と監視について情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="96922-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96922-112">この記事で説明する除外は、エンドポイントの検出と応答 (EDR) を含む、他の Defender for Endpoint for Linux 機能には適用されません。</span><span class="sxs-lookup"><span data-stu-id="96922-112">The exclusions described in this article don't apply to other Defender for Endpoint for Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="96922-113">この記事で説明する方法を使用して除外するファイルは、EDR アラートなどの検出を引き続きトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="96922-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="96922-114">特定のファイル、フォルダー、プロセス、およびプロセスで開いたファイルを Defender for Endpoint for Linux スキャンから除外できます。</span><span class="sxs-lookup"><span data-stu-id="96922-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint for Linux scans.</span></span>

<span data-ttu-id="96922-115">除外は、組織に固有またはカスタマイズされたファイルまたはソフトウェアで誤った検出を回避するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96922-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="96922-116">また、Defender for Endpoint for Linux によって引き起こされたパフォーマンスの問題を軽減する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96922-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint for Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="96922-117">除外を定義すると、Defender for Endpoint for Linux によって提供される保護が低下します。</span><span class="sxs-lookup"><span data-stu-id="96922-117">Defining exclusions lowers the protection offered by Defender for Endpoint for Linux.</span></span> <span data-ttu-id="96922-118">除外の実装に関連付けられているリスクは常に評価する必要があります。悪意がないと確信しているファイルのみを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96922-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="96922-119">サポートされる除外の種類</span><span class="sxs-lookup"><span data-stu-id="96922-119">Supported exclusion types</span></span>

<span data-ttu-id="96922-120">次の表は、Defender for Endpoint for Linux でサポートされる除外の種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="96922-120">The follow table shows the exclusion types supported by Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="96922-121">除外</span><span class="sxs-lookup"><span data-stu-id="96922-121">Exclusion</span></span> | <span data-ttu-id="96922-122">定義</span><span class="sxs-lookup"><span data-stu-id="96922-122">Definition</span></span> | <span data-ttu-id="96922-123">例</span><span class="sxs-lookup"><span data-stu-id="96922-123">Examples</span></span>
---|---|---
<span data-ttu-id="96922-124">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="96922-124">File extension</span></span> | <span data-ttu-id="96922-125">拡張子が付いたすべてのファイル(デバイス上の任意の場所)</span><span class="sxs-lookup"><span data-stu-id="96922-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="96922-126">File</span><span class="sxs-lookup"><span data-stu-id="96922-126">File</span></span> | <span data-ttu-id="96922-127">完全パスで識別される特定のファイル</span><span class="sxs-lookup"><span data-stu-id="96922-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="96922-128">フォルダー</span><span class="sxs-lookup"><span data-stu-id="96922-128">Folder</span></span> | <span data-ttu-id="96922-129">指定したフォルダーの下のすべてのファイル (再帰的)</span><span class="sxs-lookup"><span data-stu-id="96922-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="96922-130">プロセス</span><span class="sxs-lookup"><span data-stu-id="96922-130">Process</span></span> | <span data-ttu-id="96922-131">特定のプロセス (完全なパスまたはファイル名で指定) と、そのプロセスで開くすべてのファイル</span><span class="sxs-lookup"><span data-stu-id="96922-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="96922-132">正常に除外するには、上記のパスは、シンボリック リンクではなくハード リンクである必要があります。</span><span class="sxs-lookup"><span data-stu-id="96922-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="96922-133">パスがシンボリック リンクである場合は、実行して確認できます `file <path-name>` 。</span><span class="sxs-lookup"><span data-stu-id="96922-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="96922-134">ファイル、フォルダー、およびプロセスの除外は、次のワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="96922-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="96922-135">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="96922-135">Wildcard</span></span> | <span data-ttu-id="96922-136">説明</span><span class="sxs-lookup"><span data-stu-id="96922-136">Description</span></span> | <span data-ttu-id="96922-137">例</span><span class="sxs-lookup"><span data-stu-id="96922-137">Example</span></span> | <span data-ttu-id="96922-138">一致</span><span class="sxs-lookup"><span data-stu-id="96922-138">Matches</span></span> | <span data-ttu-id="96922-139">一致しない</span><span class="sxs-lookup"><span data-stu-id="96922-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="96922-140">none を含む任意の数の文字と一致します (パス内でこのワイルドカードを使用すると、1 つのフォルダーのみを置き換える点に注意してください)</span><span class="sxs-lookup"><span data-stu-id="96922-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="96922-141">?</span><span class="sxs-lookup"><span data-stu-id="96922-141">?</span></span> | <span data-ttu-id="96922-142">任意の 1 文字に一致する</span><span class="sxs-lookup"><span data-stu-id="96922-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="96922-143">除外の一覧を構成する方法</span><span class="sxs-lookup"><span data-stu-id="96922-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="96922-144">管理コンソールから</span><span class="sxs-lookup"><span data-stu-id="96922-144">From the management console</span></span>

<span data-ttu-id="96922-145">Puppet、Ansible、または別の管理コンソールから除外を構成する方法の詳細については、「Defender for Endpoint for Linux の設定」 [を参照してください](linux-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="96922-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="96922-146">コマンド ラインから</span><span class="sxs-lookup"><span data-stu-id="96922-146">From the command line</span></span>

<span data-ttu-id="96922-147">次のコマンドを実行して、除外を管理するために使用可能なスイッチを確認します。</span><span class="sxs-lookup"><span data-stu-id="96922-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="96922-148">ワイルドカードを使用して除外を構成する場合は、パラメーターを二重引用符で囲み、グローブ化を防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="96922-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="96922-149">例:</span><span class="sxs-lookup"><span data-stu-id="96922-149">Examples:</span></span>

- <span data-ttu-id="96922-150">ファイル拡張子の除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="96922-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="96922-151">ファイルの除外を追加する:</span><span class="sxs-lookup"><span data-stu-id="96922-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="96922-152">フォルダーの除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="96922-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="96922-153">ワイルドカードが含まれているフォルダーの除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="96922-153">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="96922-154">これは *、/var/* より下の 1 つのレベルのパスのみを除外しますが、より深くネストされたフォルダーは除外されません。たとえば *、/var/this-subfolder/but-not-this-subfolder*.</span><span class="sxs-lookup"><span data-stu-id="96922-154">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="96922-155">これにより、親が */var/ であるすべてのパスが除外されます*。たとえば *、/var/this-サブフォルダー/and-this-サブフォルダーも同様です*。</span><span class="sxs-lookup"><span data-stu-id="96922-155">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="96922-156">プロセスの除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="96922-156">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="96922-157">EICAR テスト ファイルを使用して除外リストを検証する</span><span class="sxs-lookup"><span data-stu-id="96922-157">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="96922-158">除外リストが機能している場合は、テスト ファイルをダウンロード `curl` して検証できます。</span><span class="sxs-lookup"><span data-stu-id="96922-158">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="96922-159">次の Bash スニペットで、除外 `test.txt` ルールに準拠したファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="96922-159">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="96922-160">たとえば、拡張機能を除外した場合は、 `.testing` に置き換 `test.txt` える `test.testing` 。</span><span class="sxs-lookup"><span data-stu-id="96922-160">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="96922-161">パスをテストする場合は、そのパス内でコマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="96922-161">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="96922-162">Defender for Endpoint for Linux がマルウェアを報告した場合、ルールは機能していません。</span><span class="sxs-lookup"><span data-stu-id="96922-162">If Defender for Endpoint for Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="96922-163">マルウェアの報告がない場合、ダウンロードしたファイルが存在する場合は、除外が機能しています。</span><span class="sxs-lookup"><span data-stu-id="96922-163">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="96922-164">ファイルを開き、EICAR テスト ファイル Web サイトで説明されている内容と内容が同じ [ことを確認できます](http://2016.eicar.org/86-0-Intended-use.html)。</span><span class="sxs-lookup"><span data-stu-id="96922-164">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="96922-165">インターネット にアクセスできない場合は、独自の EICAR テスト ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="96922-165">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="96922-166">次の Bash コマンドを使用して、EICAR 文字列を新しいテキスト ファイルに書き込む。</span><span class="sxs-lookup"><span data-stu-id="96922-166">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="96922-167">文字列を空白のテキスト ファイルにコピーして、ファイル名または除外するフォルダーに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="96922-167">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="96922-168">脅威を許可する</span><span class="sxs-lookup"><span data-stu-id="96922-168">Allow threats</span></span>

<span data-ttu-id="96922-169">特定のコンテンツをスキャン対象から除外する以外に、脅威の一部のクラス (脅威名で識別される) を検出しない製品を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="96922-169">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="96922-170">この機能を使用する場合は、デバイスの保護が解除される可能性があります。注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="96922-170">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="96922-171">許可リストに脅威名を追加するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="96922-171">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="96922-172">デバイス上の検出に関連付けられた脅威名は、次のコマンドを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="96922-172">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="96922-173">たとえば、許可リストに (EICAR 検出に関連付けられている脅威名) を追加するには、 `EICAR-Test-File (not a virus)` 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="96922-173">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
