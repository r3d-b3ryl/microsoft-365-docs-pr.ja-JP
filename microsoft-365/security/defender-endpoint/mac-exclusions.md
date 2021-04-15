---
title: Microsoft Defender ATP for Mac の除外を構成および検証する
description: Microsoft Defender ATP for Mac の除外を指定して検証します。 除外は、ファイル、フォルダー、およびプロセスに対して設定できます。
keywords: microsoft、Defender、atp、mac、除外、スキャン、ウイルス対策
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2281fccfb97d38dbdc218799b087290433deff30
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764159"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="bbe68-105">macOS 上のエンドポイント用 Microsoft Defender の除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="bbe68-105">Configure and validate exclusions for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bbe68-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bbe68-106">**Applies to:**</span></span>
- [<span data-ttu-id="bbe68-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbe68-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bbe68-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbe68-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bbe68-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="bbe68-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bbe68-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="bbe68-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="bbe68-111">この記事では、オンデマンド スキャンに適用される除外を定義する方法、およびリアルタイムの保護と監視について情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bbe68-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

>[!IMPORTANT]
><span data-ttu-id="bbe68-112">この記事で説明する除外は、エンドポイントの検出と応答 (EDR) を含む、他の Defender for Endpoint on Mac 機能には適用されません。</span><span class="sxs-lookup"><span data-stu-id="bbe68-112">The exclusions described in this article don't apply to other Defender for Endpoint on Mac capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="bbe68-113">この記事で説明する方法を使用して除外するファイルは、EDR アラートなどの検出を引き続きトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="bbe68-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="bbe68-114">特定のファイル、フォルダー、プロセス、およびプロセスで開いたファイルは、Defender for Endpoint on Mac スキャンから除外できます。</span><span class="sxs-lookup"><span data-stu-id="bbe68-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint on Mac scans.</span></span>

<span data-ttu-id="bbe68-115">除外は、組織に固有またはカスタマイズされたファイルまたはソフトウェアで誤った検出を回避するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bbe68-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="bbe68-116">また、Defender for Endpoint on Mac によるパフォーマンスの問題を軽減する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bbe68-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint on Mac.</span></span>

>[!WARNING]
><span data-ttu-id="bbe68-117">除外を定義すると、Defender for Endpoint on Mac によって提供される保護が低下します。</span><span class="sxs-lookup"><span data-stu-id="bbe68-117">Defining exclusions lowers the protection offered by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="bbe68-118">除外の実装に関連付けられているリスクは常に評価する必要があります。悪意がないと確信しているファイルのみを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe68-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="bbe68-119">サポートされる除外の種類</span><span class="sxs-lookup"><span data-stu-id="bbe68-119">Supported exclusion types</span></span>

<span data-ttu-id="bbe68-120">次の表に、Defender for Endpoint on Mac でサポートされている除外の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="bbe68-120">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="bbe68-121">除外</span><span class="sxs-lookup"><span data-stu-id="bbe68-121">Exclusion</span></span> | <span data-ttu-id="bbe68-122">定義</span><span class="sxs-lookup"><span data-stu-id="bbe68-122">Definition</span></span> | <span data-ttu-id="bbe68-123">例</span><span class="sxs-lookup"><span data-stu-id="bbe68-123">Examples</span></span>
---|---|---
<span data-ttu-id="bbe68-124">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="bbe68-124">File extension</span></span> | <span data-ttu-id="bbe68-125">拡張機能を持つすべてのファイル (コンピューター上の任意の場所)</span><span class="sxs-lookup"><span data-stu-id="bbe68-125">All files with the extension, anywhere on the machine</span></span> | `.test`
<span data-ttu-id="bbe68-126">File</span><span class="sxs-lookup"><span data-stu-id="bbe68-126">File</span></span> | <span data-ttu-id="bbe68-127">完全パスで識別される特定のファイル</span><span class="sxs-lookup"><span data-stu-id="bbe68-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="bbe68-128">フォルダー</span><span class="sxs-lookup"><span data-stu-id="bbe68-128">Folder</span></span> | <span data-ttu-id="bbe68-129">指定したフォルダーの下のすべてのファイル (再帰的)</span><span class="sxs-lookup"><span data-stu-id="bbe68-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="bbe68-130">プロセス</span><span class="sxs-lookup"><span data-stu-id="bbe68-130">Process</span></span> | <span data-ttu-id="bbe68-131">特定のプロセス (完全なパスまたはファイル名で指定) と、そのプロセスで開くすべてのファイル</span><span class="sxs-lookup"><span data-stu-id="bbe68-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

<span data-ttu-id="bbe68-132">ファイル、フォルダー、およびプロセスの除外は、次のワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bbe68-132">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="bbe68-133">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="bbe68-133">Wildcard</span></span> | <span data-ttu-id="bbe68-134">説明</span><span class="sxs-lookup"><span data-stu-id="bbe68-134">Description</span></span> | <span data-ttu-id="bbe68-135">例</span><span class="sxs-lookup"><span data-stu-id="bbe68-135">Example</span></span> | <span data-ttu-id="bbe68-136">一致</span><span class="sxs-lookup"><span data-stu-id="bbe68-136">Matches</span></span> | <span data-ttu-id="bbe68-137">一致しない</span><span class="sxs-lookup"><span data-stu-id="bbe68-137">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="bbe68-138">none を含む任意の数の文字と一致します (パス内でこのワイルドカードを使用すると、1 つのフォルダーのみを置き換える点に注意してください)</span><span class="sxs-lookup"><span data-stu-id="bbe68-138">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/*/*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="bbe68-139">?</span><span class="sxs-lookup"><span data-stu-id="bbe68-139">?</span></span> | <span data-ttu-id="bbe68-140">任意の 1 文字に一致する</span><span class="sxs-lookup"><span data-stu-id="bbe68-140">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

>[!NOTE]
><span data-ttu-id="bbe68-141">除外を評価するときに、製品は firmlinks の解決を試みる。</span><span class="sxs-lookup"><span data-stu-id="bbe68-141">The product attempts to resolve firmlinks when evaluating exclusions.</span></span> <span data-ttu-id="bbe68-142">除外にワイルドカードが含まれているか、ターゲット ファイル (ボリューム上) が存在しない場合、Firmlink 解決 `Data` は機能しません。</span><span class="sxs-lookup"><span data-stu-id="bbe68-142">Firmlink resolution does not work when the exclusion contains wildcards or the target file (on the `Data` volume) does not exist.</span></span>

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="bbe68-143">除外の一覧を構成する方法</span><span class="sxs-lookup"><span data-stu-id="bbe68-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="bbe68-144">管理コンソールから</span><span class="sxs-lookup"><span data-stu-id="bbe68-144">From the management console</span></span>

<span data-ttu-id="bbe68-145">JAMF、Intune、または別の管理コンソールから除外を構成する方法の詳細については、「Defender for Endpoint on Mac の設定」 [を参照してください](mac-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="bbe68-145">For more information on how to configure exclusions from JAMF, Intune, or another management console, see [Set preferences for Defender for Endpoint on Mac](mac-preferences.md).</span></span>

### <a name="from-the-user-interface"></a><span data-ttu-id="bbe68-146">ユーザー インターフェイスから</span><span class="sxs-lookup"><span data-stu-id="bbe68-146">From the user interface</span></span>

<span data-ttu-id="bbe68-147">Defender for Endpoint アプリケーションを開き、次のスクリーンショットに示すように、[設定の追加と削除] の [除外の管理]  >  に移動します。</span><span class="sxs-lookup"><span data-stu-id="bbe68-147">Open the Defender for Endpoint application and navigate to **Manage settings** > **Add or Remove Exclusion...**, as shown in the following screenshot:</span></span>

![除外の管理のスクリーンショット](images/mdatp-37-exclusions.png)

<span data-ttu-id="bbe68-149">追加する除外の種類を選択し、プロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="bbe68-149">Select the type of exclusion that you wish to add and follow the prompts.</span></span>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="bbe68-150">EICAR テスト ファイルを使用して除外リストを検証する</span><span class="sxs-lookup"><span data-stu-id="bbe68-150">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="bbe68-151">除外リストが機能している場合は、テスト ファイルをダウンロード `curl` して検証できます。</span><span class="sxs-lookup"><span data-stu-id="bbe68-151">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="bbe68-152">次の Bash スニペットで、除外 `test.txt` ルールに準拠したファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="bbe68-152">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="bbe68-153">たとえば、拡張機能を除外した場合は、 `.testing` に置き換 `test.txt` える `test.testing` 。</span><span class="sxs-lookup"><span data-stu-id="bbe68-153">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="bbe68-154">パスをテストする場合は、そのパス内でコマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="bbe68-154">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="bbe68-155">Defender for Endpoint on Mac でマルウェアが報告された場合、ルールは機能していません。</span><span class="sxs-lookup"><span data-stu-id="bbe68-155">If Defender for Endpoint on Mac reports malware, then the rule is not working.</span></span> <span data-ttu-id="bbe68-156">マルウェアの報告がない場合、ダウンロードしたファイルが存在する場合は、除外が機能しています。</span><span class="sxs-lookup"><span data-stu-id="bbe68-156">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="bbe68-157">ファイルを開き、EICAR テスト ファイル Web サイトで説明されている内容と内容が同じ [ことを確認できます](http://2016.eicar.org/86-0-Intended-use.html)。</span><span class="sxs-lookup"><span data-stu-id="bbe68-157">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="bbe68-158">インターネット にアクセスできない場合は、独自の EICAR テスト ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bbe68-158">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="bbe68-159">次の Bash コマンドを使用して、EICAR 文字列を新しいテキスト ファイルに書き込む。</span><span class="sxs-lookup"><span data-stu-id="bbe68-159">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="bbe68-160">文字列を空白のテキスト ファイルにコピーして、ファイル名または除外するフォルダーに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="bbe68-160">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="bbe68-161">脅威を許可する</span><span class="sxs-lookup"><span data-stu-id="bbe68-161">Allow threats</span></span>

<span data-ttu-id="bbe68-162">特定のコンテンツをスキャン対象から除外する以外に、脅威の一部のクラス (脅威名で識別される) を検出しない製品を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="bbe68-162">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="bbe68-163">この機能を使用する場合は、デバイスの保護が解除される可能性があります。注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="bbe68-163">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="bbe68-164">許可リストに脅威名を追加するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bbe68-164">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="bbe68-165">デバイス上の検出に関連付けられた脅威名は、次のコマンドを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="bbe68-165">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="bbe68-166">たとえば、許可リストに (EICAR 検出に関連付けられている脅威名) を追加するには、 `EICAR-Test-File (not a virus)` 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bbe68-166">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
