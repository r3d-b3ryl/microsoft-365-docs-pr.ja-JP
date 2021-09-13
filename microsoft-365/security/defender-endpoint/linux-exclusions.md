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
ms.openlocfilehash: 269f74b0df2b0c51217d44bdb0cc2001d0f8a34d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189500"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a>Linux 上のエンドポイント向け Microsoft Defender の除外を構成および検証する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

この記事では、オンデマンド スキャンに適用される除外を定義する方法、およびリアルタイムの保護と監視について情報を提供します。

> [!IMPORTANT]
> この記事で説明する除外は、エンドポイントの検出と応答 (EDR) を含む、他の Defender for Endpoint on Linux 機能には適用EDR。 この記事で説明する方法を使用して除外するファイルは、アラートや他の検出EDRトリガーできます。

特定のファイル、フォルダー、プロセス、およびプロセスが開いたファイルは、Defender for Endpoint on Linux スキャンから除外できます。

除外は、組織に固有またはカスタマイズされたファイルまたはソフトウェアで誤った検出を回避するために役立ちます。 また、Defender for Endpoint on Linux によって引き起こされたパフォーマンスの問題を軽減する場合にも役立ちます。

> [!WARNING]
> 除外を定義すると、Defender for Endpoint on Linux によって提供される保護が低下します。 除外の実装に関連付けられているリスクは常に評価する必要があります。悪意がないと確信しているファイルのみを除外する必要があります。

## <a name="supported-exclusion-types"></a>サポートされる除外の種類

次の表に、Defender for Endpoint on Linux でサポートされる除外の種類を示します。

除外|定義|例
---|---|---
ファイル拡張子|拡張子が付いたすべてのファイル(デバイス上の任意の場所)|`.test`
ファイル|完全パスで識別される特定のファイル|`/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
フォルダー|指定したフォルダーの下のすべてのファイル (再帰的)|`/var/log/`<br/>`/var/*/`
プロセス|特定のプロセス (完全なパスまたはファイル名で指定) と、そのプロセスで開くすべてのファイル|`/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> 正常に除外するには、上記のパスは、シンボリック リンクではなくハード リンクである必要があります。 パスがシンボリック リンクである場合は、実行して確認できます `file <path-name>` 。

ファイル、フォルダー、およびプロセスの除外は、次のワイルドカードをサポートします。

ワイルドカード|説明|例|一致|一致しない
---|---|---|---|---
\*|none を含む任意の数の文字と一致します (パス内でこのワイルドカードを使用すると、1 つのフォルダーのみを置き換える点に注意してください)|`/var/\*/\*.log`|`/var/log/system.log`|`/var/log/nested/system.log`
?|任意の 1 文字に一致する|`file?.log`|`file1.log`<br/>`file2.log`|`file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a>除外の一覧を構成する方法

### <a name="from-the-management-console"></a>管理コンソールから

Puppet、Ansible、または別の管理コンソールから除外を構成する方法の詳細については、「Linux での Defender for Endpoint の設定」 [を参照してください](linux-preferences.md)。

### <a name="from-the-command-line"></a>コマンド ラインから

次のコマンドを実行して、除外を管理するために使用可能なスイッチを確認します。

```bash
mdatp exclusion
```

> [!TIP]
> ワイルドカードを使用して除外を構成する場合は、パラメーターを二重引用符で囲み、グローブ化を防ぐ必要があります。

例:

- ファイル拡張子の除外を追加します。

    ```bash
    mdatp exclusion extension add --name .txt
    ```

    ```Output
    Extension exclusion configured successfully
    ```

- ファイルの除外を追加する:

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

- ワイルドカードが含まれているフォルダーの除外を追加します。

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > これは *、/var/* より下の 1 つのレベルのパスのみを除外しますが、より深くネストされたフォルダーは除外されません。たとえば *、/var/this-subfolder/but-not-this-subfolder*.

    ```bash
    mdatp exclusion folder add --path "/var/"
    ```

    > [!NOTE]
    > これにより、親が */var/ であるすべてのパスが除外されます*。たとえば *、/var/this-サブフォルダー/and-this-サブフォルダーも同様です*。

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

除外リストが機能している場合は、テスト ファイルをダウンロード `curl` して検証できます。

次の Bash スニペットで、除外 `test.txt` ルールに準拠したファイルに置き換えます。 たとえば、拡張機能を除外した場合は、 `.testing` に置き換 `test.txt` える `test.testing` 。 パスをテストする場合は、そのパス内でコマンドを実行してください。

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Defender for Endpoint on Linux がマルウェアを報告した場合、ルールは機能していません。 マルウェアの報告がない場合、ダウンロードしたファイルが存在する場合は、除外が機能しています。 ファイルを開き、EICAR テスト ファイル Web サイトで説明されている内容と内容が同じ [ことを確認できます](http://2016.eicar.org/86-0-Intended-use.html)。

インターネット にアクセスできない場合は、独自の EICAR テスト ファイルを作成できます。 次の Bash コマンドを使用して、EICAR 文字列を新しいテキスト ファイルに書き込む。

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

文字列を空白のテキスト ファイルにコピーして、ファイル名または除外するフォルダーに保存することもできます。

## <a name="allow-threats"></a>脅威を許可する

特定のコンテンツをスキャン対象から除外する以外に、脅威の一部のクラス (脅威名で識別される) を検出しない製品を構成することもできます。 この機能を使用する場合は、デバイスの保護が解除される可能性があります。注意が必要です。

許可リストに脅威名を追加するには、次のコマンドを実行します。

```bash
mdatp threat allowed add --name [threat-name]
```

デバイス上の検出に関連付けられた脅威名は、次のコマンドを使用して取得できます。

```bash
mdatp threat list
```

たとえば、許可リストに (EICAR 検出に関連付けられている脅威名) を追加するには、 `EICAR-Test-File (not a virus)` 次のコマンドを実行します。

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
