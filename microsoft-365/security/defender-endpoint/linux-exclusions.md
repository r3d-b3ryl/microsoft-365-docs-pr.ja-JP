---
title: Linux 上のエンドポイント向け Microsoft Defender の除外を構成および検証する
description: Linux 上のエンドポイント用 Microsoft Defender の除外を指定して検証します。 除外は、ファイル、フォルダー、およびプロセスに対して設定できます。
keywords: microsoft、defender、Microsoft Defender for Endpoint、Linux、除外、スキャン、ウイルス対策
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
ms.openlocfilehash: b55572509e9837f2858f96b01a13fbf259b2b770
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393789"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="244c6-105">Linux 上のエンドポイント向け Microsoft Defender の除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="244c6-105">Configure and validate exclusions for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="244c6-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="244c6-106">**Applies to:**</span></span>

- [<span data-ttu-id="244c6-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="244c6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="244c6-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="244c6-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="244c6-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="244c6-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="244c6-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="244c6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="244c6-111">この記事では、オンデマンド スキャンに適用される除外を定義する方法、およびリアルタイムの保護と監視について情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="244c6-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="244c6-112">この記事で説明する除外は、エンドポイントの検出と応答 (EDR) を含む、他の Defender for Endpoint on Linux 機能には適用EDR。</span><span class="sxs-lookup"><span data-stu-id="244c6-112">The exclusions described in this article don't apply to other Defender for Endpoint on Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="244c6-113">この記事で説明する方法を使用して除外するファイルは、アラートや他の検出EDRトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="244c6-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="244c6-114">特定のファイル、フォルダー、プロセス、およびプロセスが開いたファイルは、Defender for Endpoint on Linux スキャンから除外できます。</span><span class="sxs-lookup"><span data-stu-id="244c6-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint on Linux scans.</span></span>

<span data-ttu-id="244c6-115">除外は、組織に固有またはカスタマイズされたファイルまたはソフトウェアで誤った検出を回避するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="244c6-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="244c6-116">また、Defender for Endpoint on Linux によって引き起こされたパフォーマンスの問題を軽減する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="244c6-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint on Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="244c6-117">除外を定義すると、Defender for Endpoint on Linux によって提供される保護が低下します。</span><span class="sxs-lookup"><span data-stu-id="244c6-117">Defining exclusions lowers the protection offered by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="244c6-118">除外の実装に関連付けられているリスクは常に評価する必要があります。悪意がないと確信しているファイルのみを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="244c6-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="244c6-119">サポートされる除外の種類</span><span class="sxs-lookup"><span data-stu-id="244c6-119">Supported exclusion types</span></span>

<span data-ttu-id="244c6-120">次の表に、Defender for Endpoint on Linux でサポートされる除外の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="244c6-120">The follow table shows the exclusion types supported by Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="244c6-121">除外</span><span class="sxs-lookup"><span data-stu-id="244c6-121">Exclusion</span></span> | <span data-ttu-id="244c6-122">定義</span><span class="sxs-lookup"><span data-stu-id="244c6-122">Definition</span></span> | <span data-ttu-id="244c6-123">例</span><span class="sxs-lookup"><span data-stu-id="244c6-123">Examples</span></span>
---|---|---
<span data-ttu-id="244c6-124">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="244c6-124">File extension</span></span> | <span data-ttu-id="244c6-125">拡張子が付いたすべてのファイル(デバイス上の任意の場所)</span><span class="sxs-lookup"><span data-stu-id="244c6-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="244c6-126">ファイル</span><span class="sxs-lookup"><span data-stu-id="244c6-126">File</span></span> | <span data-ttu-id="244c6-127">完全パスで識別される特定のファイル</span><span class="sxs-lookup"><span data-stu-id="244c6-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="244c6-128">フォルダー</span><span class="sxs-lookup"><span data-stu-id="244c6-128">Folder</span></span> | <span data-ttu-id="244c6-129">指定したフォルダーの下のすべてのファイル (再帰的)</span><span class="sxs-lookup"><span data-stu-id="244c6-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="244c6-130">プロセス</span><span class="sxs-lookup"><span data-stu-id="244c6-130">Process</span></span> | <span data-ttu-id="244c6-131">特定のプロセス (完全なパスまたはファイル名で指定) と、そのプロセスで開くすべてのファイル</span><span class="sxs-lookup"><span data-stu-id="244c6-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="244c6-132">正常に除外するには、上記のパスは、シンボリック リンクではなくハード リンクである必要があります。</span><span class="sxs-lookup"><span data-stu-id="244c6-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="244c6-133">パスがシンボリック リンクである場合は、実行して確認できます `file <path-name>` 。</span><span class="sxs-lookup"><span data-stu-id="244c6-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="244c6-134">ファイル、フォルダー、およびプロセスの除外は、次のワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="244c6-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="244c6-135">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="244c6-135">Wildcard</span></span> | <span data-ttu-id="244c6-136">説明</span><span class="sxs-lookup"><span data-stu-id="244c6-136">Description</span></span> | <span data-ttu-id="244c6-137">例</span><span class="sxs-lookup"><span data-stu-id="244c6-137">Example</span></span> | <span data-ttu-id="244c6-138">一致</span><span class="sxs-lookup"><span data-stu-id="244c6-138">Matches</span></span> | <span data-ttu-id="244c6-139">一致しない</span><span class="sxs-lookup"><span data-stu-id="244c6-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="244c6-140">none を含む任意の数の文字と一致します (パス内でこのワイルドカードを使用すると、1 つのフォルダーのみを置き換える点に注意してください)</span><span class="sxs-lookup"><span data-stu-id="244c6-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="244c6-141">?</span><span class="sxs-lookup"><span data-stu-id="244c6-141">?</span></span> | <span data-ttu-id="244c6-142">任意の 1 文字に一致する</span><span class="sxs-lookup"><span data-stu-id="244c6-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="244c6-143">除外の一覧を構成する方法</span><span class="sxs-lookup"><span data-stu-id="244c6-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="244c6-144">管理コンソールから</span><span class="sxs-lookup"><span data-stu-id="244c6-144">From the management console</span></span>

<span data-ttu-id="244c6-145">Puppet、Ansible、または別の管理コンソールから除外を構成する方法の詳細については、「Linux での Defender for Endpoint の設定」 [を参照してください](linux-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="244c6-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="244c6-146">コマンド ラインから</span><span class="sxs-lookup"><span data-stu-id="244c6-146">From the command line</span></span>

<span data-ttu-id="244c6-147">次のコマンドを実行して、除外を管理するために使用可能なスイッチを確認します。</span><span class="sxs-lookup"><span data-stu-id="244c6-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="244c6-148">ワイルドカードを使用して除外を構成する場合は、パラメーターを二重引用符で囲み、グローブ化を防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="244c6-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="244c6-149">例:</span><span class="sxs-lookup"><span data-stu-id="244c6-149">Examples:</span></span>

- <span data-ttu-id="244c6-150">ファイル拡張子の除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="244c6-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="244c6-151">ファイルの除外を追加する:</span><span class="sxs-lookup"><span data-stu-id="244c6-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="244c6-152">フォルダーの除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="244c6-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```


- <span data-ttu-id="244c6-153">2 番目のフォルダーの除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="244c6-153">Add an exclusion for a second folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    mdatp exclusion folder add --path /other/folder
    ```
    ```Output
    Folder exclusion configured successfully
    ```


- <span data-ttu-id="244c6-154">ワイルドカードが含まれているフォルダーの除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="244c6-154">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="244c6-155">これは *、/var/* より下の 1 つのレベルのパスのみを除外しますが、より深くネストされたフォルダーは除外されません。たとえば *、/var/this-subfolder/but-not-this-subfolder*.</span><span class="sxs-lookup"><span data-stu-id="244c6-155">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="244c6-156">これにより、親が */var/ であるすべてのパスが除外されます*。たとえば *、/var/this-サブフォルダー/and-this-サブフォルダーも同様です*。</span><span class="sxs-lookup"><span data-stu-id="244c6-156">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="244c6-157">プロセスの除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="244c6-157">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```


- <span data-ttu-id="244c6-158">2 番目のプロセスの除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="244c6-158">Add an exclusion for a second process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    mdatp exclusion process add --name dog
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="244c6-159">EICAR テスト ファイルを使用して除外リストを検証する</span><span class="sxs-lookup"><span data-stu-id="244c6-159">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="244c6-160">除外リストが機能している場合は、テスト ファイルをダウンロード `curl` して検証できます。</span><span class="sxs-lookup"><span data-stu-id="244c6-160">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="244c6-161">次の Bash スニペットで、除外 `test.txt` ルールに準拠したファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="244c6-161">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="244c6-162">たとえば、拡張機能を除外した場合は、 `.testing` に置き換 `test.txt` える `test.testing` 。</span><span class="sxs-lookup"><span data-stu-id="244c6-162">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="244c6-163">パスをテストする場合は、そのパス内でコマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="244c6-163">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="244c6-164">Defender for Endpoint on Linux がマルウェアを報告した場合、ルールは機能していません。</span><span class="sxs-lookup"><span data-stu-id="244c6-164">If Defender for Endpoint on Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="244c6-165">マルウェアの報告がない場合、ダウンロードしたファイルが存在する場合は、除外が機能しています。</span><span class="sxs-lookup"><span data-stu-id="244c6-165">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="244c6-166">ファイルを開き、EICAR テスト ファイル Web サイトで説明されている内容と内容が同じ [ことを確認できます](http://2016.eicar.org/86-0-Intended-use.html)。</span><span class="sxs-lookup"><span data-stu-id="244c6-166">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="244c6-167">インターネット にアクセスできない場合は、独自の EICAR テスト ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="244c6-167">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="244c6-168">次の Bash コマンドを使用して、EICAR 文字列を新しいテキスト ファイルに書き込む。</span><span class="sxs-lookup"><span data-stu-id="244c6-168">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="244c6-169">文字列を空白のテキスト ファイルにコピーして、ファイル名または除外するフォルダーに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="244c6-169">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="244c6-170">脅威を許可する</span><span class="sxs-lookup"><span data-stu-id="244c6-170">Allow threats</span></span>

<span data-ttu-id="244c6-171">特定のコンテンツをスキャン対象から除外する以外に、脅威の一部のクラス (脅威名で識別される) を検出しない製品を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="244c6-171">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="244c6-172">この機能を使用する場合は、デバイスの保護が解除される可能性があります。注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="244c6-172">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="244c6-173">許可リストに脅威名を追加するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="244c6-173">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="244c6-174">デバイス上の検出に関連付けられた脅威名は、次のコマンドを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="244c6-174">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="244c6-175">たとえば、許可リストに (EICAR 検出に関連付けられている脅威名) を追加するには、 `EICAR-Test-File (not a virus)` 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="244c6-175">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
