---
title: Linux でのMicrosoft Defender for Endpointの除外の構成と検証
description: Linux 上のMicrosoft Defender for Endpointの除外を指定して検証します。 除外は、ファイル、フォルダー、およびプロセスに対して設定できます。
keywords: microsoft, defender, Microsoft Defender for Endpoint, Linux, 除外, スキャン, ウイルス対策
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b86cad016af0f7819d69f0156498336652e6292d
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/29/2021
ms.locfileid: "61218108"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a>Linux でのMicrosoft Defender for Endpointの除外の構成と検証

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

この記事では、オンデマンド スキャンに適用される除外を定義する方法と、リアルタイムの保護と監視について説明します。

> [!IMPORTANT]
> この記事で説明する除外は、エンドポイントでの検出と対応 (EDR) を含む Linux 上の他の Defender for Endpoint 機能には適用されません。 この記事で説明する方法を使用して除外したファイルは、引き続きEDRアラートやその他の検出をトリガーできます。

特定のファイル、フォルダー、プロセス、およびプロセスで開かれたファイルは、Defender for Endpoint on Linux スキャンから除外できます。

除外は、組織に固有またはカスタマイズされたファイルまたはソフトウェアで誤った検出を回避するために役立ちます。 また、Defender for Endpoint on Linux によって引き起こされるパフォーマンスの問題を軽減する場合にも役立ちます。

> [!WARNING]
> 除外を定義すると、Defender for Endpoint on Linux によって提供される保護が低下します。 除外の実装に関連するリスクは常に評価する必要があります。また、悪意のないと確信しているファイルのみを除外する必要があります。

## <a name="supported-exclusion-types"></a>サポートされている除外の種類

次の表に、Defender for Endpoint on Linux でサポートされている除外の種類を示します。

除外|定義|例
---|---|---
ファイル拡張子|拡張機能を持つすべてのファイル(デバイス上の任意の場所)|`.test`
ファイル|完全パスで識別される特定のファイル|`/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
フォルダー|指定したフォルダーの下にあるすべてのファイル (再帰的)|`/var/log/`<br/>`/var/*/`
プロセス|特定のプロセス (完全なパスまたはファイル名で指定) とそのプロセスによって開かれたすべてのファイル|`/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> 正しく除外するには、上記のパスはシンボリック リンクではなくハード リンクである必要があります。 パスがシンボリック リンクであるかどうかを確認するには、次を実行します `file <path-name>`。

ファイル、フォルダー、およびプロセスの除外では、次のワイルドカードがサポートされます。

ワイルドカード|説明|例|一致|一致しない
---|---|---|---|---
\*|none を含む任意の数の文字と一致します (パス内でこのワイルドカードを使用すると、フォルダーは 1 つのみ置き換えられます)|`/var/\*/\*.log`|`/var/log/system.log`|`/var/log/nested/system.log`
?|任意の 1 文字に一致します|`file?.log`|`file1.log`<br/>`file2.log`|`file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a>除外の一覧を構成する方法

### <a name="from-the-management-console"></a>管理コンソールから

Puppet、Ansible、またはその他の管理コンソールから除外を構成する方法の詳細については、「 [Defender for Endpoint on Linux の基本設定を設定](linux-preferences.md)する」を参照してください。

### <a name="from-the-command-line"></a>コマンド ラインから

次のコマンドを実行して、除外を管理するために使用可能なスイッチを確認します。

```bash
mdatp exclusion
```

> [!TIP]
> ワイルドカードを使用して除外を構成する場合は、グローブを防ぐためにパラメーターを二重引用符で囲みます。

例:

- ファイル拡張子の除外を追加します。

    ```bash
    mdatp exclusion extension add --name .txt
    ```

    ```Output
    Extension exclusion configured successfully
    ```

- ファイルの除外を追加します。

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```

    ```Output
    File exclusion configured successfully
    ```

- フォルダーの除外を追加します。

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```

    ```Output
    Folder exclusion configured successfully
    ```

- 2 番目のフォルダーの除外を追加します。

    ```bash
    mdatp exclusion folder add --path /var/log/
    mdatp exclusion folder add --path /other/folder
    ```

    ```Output
    Folder exclusion configured successfully
    ```

- ワイルドカードが含まれるフォルダーの除外を追加します。

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > これにより、 */var/* の下の 1 レベルのパスのみが除外されますが、より深く入れ子になっているフォルダーは除外されません。たとえば、 */var/this-subfolder/but-not-this-subfolder などです*。

    ```bash
    mdatp exclusion folder add --path "/var/"
    ```

    > [!NOTE]
    > これにより、親が */var/*; であるすべてのパスが除外されます。たとえば、 */var/this-subfolder/and-this-this-サブフォルダーも同様です*。

    ```Output
    Folder exclusion configured successfully
    ```

- プロセスの除外を追加します。

    ```bash
    mdatp exclusion process add --name cat
    ```

    ```Output
    Process exclusion configured successfully
    ```

- 2 番目のプロセスの除外を追加します。

    ```bash
    mdatp exclusion process add --name cat
    mdatp exclusion process add --name dog
    ```

    ```Output
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>EICAR テスト ファイルを使用して除外リストを検証する

テスト ファイルをダウンロードするために使用 `curl` することで、除外リストが機能していることを検証できます。

次の Bash スニペットでは、除外規則に準拠するファイルに置き換えます `test.txt` 。 たとえば、拡張機能を除外した場合は、次のように`.testing``test.testing`置き換えます`test.txt`。 パスをテストする場合は、そのパス内でコマンドを実行していることを確認します。

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Defender for Endpoint on Linux でマルウェアが報告された場合、ルールは機能しません。 マルウェアのレポートがなく、ダウンロードしたファイルが存在する場合は、除外が機能します。 ファイルを開いて、 [EICAR テスト ファイル Web サイト](http://2016.eicar.org/86-0-Intended-use.html)で説明されている内容と内容が同じであることを確認できます。

インターネットにアクセスできない場合は、独自の EICAR テスト ファイルを作成できます。 次の Bash コマンドを使用して、EICAR 文字列を新しいテキスト ファイルに書き込みます。

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

文字列を空白のテキスト ファイルにコピーし、ファイル名または除外しようとしているフォルダーに保存することもできます。

## <a name="allow-threats"></a>脅威を許可する

特定のコンテンツをスキャン対象から除外するだけでなく、一部のクラスの脅威を検出しないように製品を構成することもできます (脅威名で識別)。 デバイスが保護されていない状態になる可能性があるため、この機能を使用する場合は注意が必要です。

許可されたリストに脅威名を追加するには、次のコマンドを実行します。

```bash
mdatp threat allowed add --name [threat-name]
```

デバイス上の検出に関連付けられている脅威名は、次のコマンドを使用して取得できます。

```bash
mdatp threat list
```

たとえば、許可されたリストに (EICAR 検出に関連付けられた脅威名) を追加 `EICAR-Test-File (not a virus)` するには、次のコマンドを実行します。

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
