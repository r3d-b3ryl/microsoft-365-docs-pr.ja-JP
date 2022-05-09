---
title: Mac でMicrosoft Defender for Endpointの除外を構成および検証する
description: Mac でMicrosoft Defender for Endpointの除外を指定して検証します。 除外は、ファイル、フォルダー、およびプロセスに対して設定できます。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, 除外, スキャン, ウイルス対策
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
ms.openlocfilehash: bc16b601181775b3b12f1db0fcceecaa2bca33a8
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474093"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-macos"></a>macOS でのMicrosoft Defender for Endpointの除外の構成と検証

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

この記事では、オンデマンド スキャンに適用される除外を定義する方法と、リアルタイムの保護と監視について説明します。

> [!IMPORTANT]
> この記事で説明する除外は、エンドポイントでの検出と対応 (EDR) を含む他の Defender for Endpoint on Mac 機能には適用されません。 この記事で説明する方法を使用して除外したファイルは、引き続きEDRアラートやその他の検出をトリガーできます。

特定のファイル、フォルダー、プロセス、およびプロセスで開かれたファイルは、Defender for Endpoint on Mac スキャンから除外できます。

除外は、組織に固有またはカスタマイズされたファイルまたはソフトウェアで誤った検出を回避するために役立ちます。 また、Defender for Endpoint on Mac によって引き起こされるパフォーマンスの問題を軽減する場合にも役立ちます。

> [!WARNING]
> 除外を定義すると、Defender for Endpoint on Mac によって提供される保護が低下します。 除外の実装に関連するリスクは常に評価する必要があります。また、悪意のないと確信しているファイルのみを除外する必要があります。

## <a name="supported-exclusion-types"></a>サポートされている除外の種類

次の表は、Defender for Endpoint on Mac でサポートされている除外の種類を示しています。

除外|定義|例
---|---|---
ファイル拡張子|拡張機能を持つすべてのファイル(コンピューター上の任意の場所)|`.test`
ファイル|完全パスで識別される特定のファイル|`/var/log/test.log` <p> `/var/log/*.log` <p> `/var/log/install.?.log`
フォルダー|指定したフォルダーの下にあるすべてのファイル (再帰的)|`/var/log/` <p> `/var/*/`
プロセス|特定のプロセス (完全なパスまたはファイル名で指定) とそのプロセスによって開かれたすべてのファイル|`/bin/cat` <p> `cat` <p> `c?t`

ファイル、フォルダー、およびプロセスの除外では、次のワイルドカードがサポートされます。

ワイルドカード|説明|例|一致|一致しない
---|---|---|---|---
\*|none を含む任意の数の文字と一致します (パス内でこのワイルドカードを使用すると、フォルダーは 1 つのみ置き換えられます)|`/var/*/*.log`|`/var/log/system.log`|`/var/log/nested/system.log`
?|任意の 1 文字に一致します|`file?.log`|`file1.log` <p> `file2.log`|`file123.log`

> [!NOTE]
> 製品は、除外を評価するときに firmlinks を解決しようとします。 除外にワイルドカードが含まれているか、ターゲット ファイル (ボリューム上) が存在しない場合、Firmlink 解決 `Data` は機能しません。

## <a name="how-to-configure-the-list-of-exclusions"></a>除外の一覧を構成する方法

### <a name="from-the-management-console"></a>管理コンソールから

JAMF、Intune、またはその他の管理コンソールからの除外を構成する方法の詳細については、「[Defender for Endpoint on Mac の基本設定を設定](mac-preferences.md)する」を参照してください。

### <a name="from-the-user-interface"></a>ユーザー インターフェイスから

次のスクリーンショットに示すように、Defender for Endpoint アプリケーションを開き **、[管理設定** \> **の追加と除外の削除...**] に移動します。

:::image type="content" source="images/mdatp-37-exclusions.png" alt-text="[除外の管理] ページ" lightbox="images/mdatp-37-exclusions.png":::

追加する除外の種類を選択し、プロンプトに従います。

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>EICAR テスト ファイルを使用して除外リストを検証する

テスト ファイルをダウンロードするために使用 `curl` することで、除外リストが機能していることを検証できます。

次の Bash スニペットでは、除外規則に準拠するファイルに置き換えます `test.txt` 。 たとえば、拡張機能を除外した場合は、次のように`.testing``test.testing`置き換えます`test.txt`。 パスをテストする場合は、そのパス内でコマンドを実行していることを確認します。

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Mac 上の Defender for Endpoint がマルウェアを報告した場合、ルールは機能しません。 マルウェアのレポートがなく、ダウンロードしたファイルが存在する場合は、除外が機能します。 ファイルを開いて、 [EICAR テスト ファイル Web サイト](http://2016.eicar.org/86-0-Intended-use.html)で説明されている内容と内容が同じであることを確認できます。

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
