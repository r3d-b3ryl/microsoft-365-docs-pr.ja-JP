---
title: Microsoft Defender for Endpoint - 脅威と脆弱性の管理の Log4Shell の脆弱性を軽減する方法について説明します
description: Microsoft Defender for Endpointの Log4Shell の脆弱性を軽減する方法について説明します
keywords: tvm、lo4j
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365-initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c6564d191b3d3302f818e20fe08e64b415c2b0bb
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65131367"
---
# <a name="learn-how-to-manage-the-log4shell-vulnerability-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointで Log4Shell の脆弱性を管理する方法について説明します

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Log4Shell の脆弱性は、Apache Log4j 2 ログ ライブラリで見つかったリモートコード実行 (RCE) の脆弱性です。 Apache Log4j 2 は多くのソフトウェア アプリケーションやオンライン サービスで一般的に使用されているため、世界中の企業にとって複雑でリスクの高い状況を表します。 "Log4Shell" ([CVE-2021-44228](https://cve.mitre.org/cgi-bin/cvename.cgi?name=2021-44228)、 [CVE-2021-45046](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-45046) ) と呼ばれ、攻撃者が悪用してデータを抽出し、組織にランサムウェアをデプロイできる新しい攻撃ベクトルが導入されています。

> [!NOTE]
> 組織を保護するための脆弱性と製品固有の軽減策に関するガイダンスと技術情報については [、Log4j 2 脆弱性の悪用の防止、検出、および捜索](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/)に関するブログガイダンスと [Microsoft Security Response Center](https://msrc-blog.microsoft.com/2021/12/11/microsofts-response-to-cve-2021-44228-apache-log4j2/) を参照してください。

## <a name="overview-of-discovery-monitoring-and-mitigation-capabilities"></a>検出、監視、軽減機能の概要

脅威と脆弱性の管理には、Log4Shell の脆弱性に対する組織の公開を特定、監視、軽減するのに役立つ次の機能が用意されています。

- **検出**: 公開されているデバイス (Microsoft Defender for Endpointオンボードされたデバイスと、検出されたがまだオンボードされていないデバイスの両方) の検出は、ディスク上で検出された脆弱なソフトウェアと脆弱なファイルに基づいています。
- **脅威の認識:** 組織の露出を評価するための統合ビュー。 このビューには、デバイス レベルとソフトウェア レベルでの公開が表示され、最後に表示された日時、最後に実行された日時、開いているポートで最後に実行された時刻など、脆弱なファイルの詳細にアクセスできます。 この情報を使用して、修復アクションに優先順位を付けることができます。 公開されているデバイスに関連するデータがダッシュボードに表示されるまでには、最大で 24 時間かかる場合があります。
- **軽減策のオプション:** 軽減策オプションを適用して、露出リスクを軽減します。
- **高度なハンティング:** 高度な捜索を使用して、ディスク上で識別された脆弱な log4j ファイルの詳細を返します。

> [!NOTE]
> これらの機能は、Windows 10 & Windows 11、Windows Server、Linux、macOS でサポートされています。
>
> Linux でのサポートには Microsoft Defender for Endpoint、Linux クライアント バージョン 101.52.57 (30.121092.15257.0) 以降が必要です。
>
> macOS でのサポートには、macOS クライアント バージョン 20.121111.15416.0 以降Microsoft Defender for Endpoint必要があります。
>
>サポートされているバージョンの詳細については、「 [サポートされているオペレーティング システムのプラットフォームと機能](tvm-supported-os.md)」を参照してください。

## <a name="exposed-devices-discovery"></a>公開されたデバイスの検出

組み込み脅威と脆弱性の管理機能は、log4j 検出を有効にするだけでなく、Microsoft 365 Defender ポータルで Log4Shell の脆弱性にさらされているデバイスを検出するのに役立ちます。

オンボードされたデバイスは、脆弱なソフトウェアとファイルを検出できる既存の埋め込み脅威と脆弱性の管理機能を使用して評価されます。

検出されたがまだオンボードされていないデバイスで検出するには、Log4j 検出を有効にする必要があります。 これにより、デバイス検出がネットワークをアクティブにプローブするのと同じ方法でプローブが開始されます。 これには、複数のオンボード エンドポイント (Windows 10+ および Windows Server 2019+ デバイス) からのプローブと、CVE-2021-44228 に対して脆弱でリモートで公開されているデバイスを検出するためのサブネット内でのプローブのみが含まれます。

Log4 検出を有効にするには:

1. **設定** > **Device discoveryDiscovery** >  **のセットアップ** に移動します
2. **Log4j2 検出を有効にする (CVE-2021-44228)** を選択します
3. **[保存]** を選びます。

:::image type="content" source="images/enable_log4j.png" alt-text="log4j2 検出を有効にする設定" lightbox="images/enable_log4j.png":::

これらのプローブを実行すると、プローブ対象のデバイスまたはプローブ デバイスに有害な影響を与えることなく、標準の Log4j フローがトリガーされます。 プローブ自体は、検出されたデバイスに複数の HTTP 要求を送信し、一般的な Web アプリケーション ポート (たとえば、80,8000,8080,443,8443) と URL をターゲットにして行われます。 要求には、プローブされたマシンからの DNS 要求をトリガーする JNDI ペイロードを持つ HTTP ヘッダーが含まれています。

たとえば、ユーザー エージェント: ${jndi:dns://192.168.1.3:5353/MDEDiscoveryUser-Agent} (192.168.1.3 はプローブ マシンの IP) です。

> [!NOTE]
> Log4j2 検出を有効にすると、オンボードされたデバイスが自己プローブを使用してローカルの脆弱性を検出することも意味します。

## <a name="vulnerable-software-and-files-detection"></a>脆弱なソフトウェアとファイルの検出

脅威と脆弱性の管理には、検出に役立つレイヤーが用意されています。

- **脆弱なソフトウェア**: 検出は、Log4j リモート コードの実行に対して脆弱であることが知られているインストール済みのアプリケーション Common Platform 列挙型 (CPE) に基づいています。
- **脆弱なファイル:** メモリ内のファイルとファイル システム内のファイルの両方が評価されます。 これらのファイルには、既知の脆弱なバージョンの Log4j コア jar ファイル、または脆弱な jndi ルックアップ クラスまたは脆弱な log4j コア ファイルを含む Uber-JAR を使用できます。 具体的には、次のようになります。

  - JAR ファイルに脆弱な Log4j ファイルが含まれているかどうかを判断するには、JAR ファイルを調べて、次のファイル \\(META-INFmavenorg.apache.logging.log4jlog4j-corepom.properties\\\\\\\\) を検索します。このファイルが存在する場合は、Log4j バージョンが読み取られ、抽出されます。
  - 文字列 "/log4j/core/lookup/JndiLookup.class" を含むパスを探して JAR ファイル内の JndiLookup.class ファイルを検索します。JndiLookup.class ファイルが存在する場合、脅威と脆弱性の管理は、この JAR に pom.properties で定義されたバージョンの Log4j ファイルが含まれているかどうかを判断します。
  - は、次のいずれかの文字列を含むパスを検索して、入れ子になった JAR 内に埋め込まれた脆弱な Log4j コア JAR ファイルを検索します。
    - lib/log4j-core-
    - WEB-INF/lib/log4j-core-
    - App-INF/lib/log4j-core-

次の表では、サポートされているプラットフォームとバージョンの検索機能について説明します。

|機能|ファイルの種類|Windows10 以降、<br>server2019+|Server 2012R2,<br>server2016|Server 2008R2|Linux + macOS|
|:---|:---|:---|:---|:---|:---|
|メモリ内の検索  | Log4j-core | はい |はい<sup>[1]| - | はい |
| |Uber-JARs | はい |はい<sup>[1]| - | はい |
| ディスク上のすべてのファイルを検索する  |Log4j-core | はい |はい<sup>[1]| はい | - |
| | Uber-JARs|はい |はい<sup>[1]| - | -|

(1) 機能は、[KB5005292 が Windows Server 2012 R2](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac) および 2016 にインストールされている場合に使用できます。

## <a name="learn-about-your-log4shell-exposure-and-mitigation-options"></a>Log4Shell の公開オプションと軽減策のオプションについて説明します

### <a name="threat-and-vulnerability-management-dashboard"></a>脅威と脆弱性の管理ダッシュボード

脅威と脆弱性の管理 ダッシュボードを使用して、現在の露出を確認します。

1. Microsoft 365 Defender ポータルで、**脆弱性管理** > **DashboardThreat** >  **awareness:**
:::image type="content" source="images/awareness_dashboard.png" alt-text="脆弱性の管理 ダッシュボードの脅威認識ウィジェットに" lightbox="images/awareness_dashboard.png":::移動します
2. [ **脆弱性の詳細の表示** ] を選択して、組織の公開の統合ビューを表示します。
:::image type="content" source="images/view_vulnerability_details.png" alt-text="CVE-2021-44228 (Log4j) の脆弱性の詳細ページ" lightbox="images/view_vulnerability_details.png":::
3. 関連するタブを選択すると、露出が次のように分割されます。
    - 公開されたデバイス – オンボード
    - 公開されたデバイス – オンボードされていない
    - 脆弱なファイル
    - 脆弱なソフトウェア

### <a name="log4shell-vulnerability-mitigation"></a>Log4Shell の脆弱性の軽減策

log4Shell の脆弱性は、既定の構成で Log4j バージョン 2.10 - 2.14.1 の JNDI ルックアップを防止することで軽減できます。 この軽減アクションを作成するには、 **脅威認識ダッシュボード** から次の手順を実行します。

1. [**脆弱性の詳細の表示**] を選択します
2. **軽減策オプションを選択する**

すべての公開デバイスに軽減策を適用するか、特定のオンボード デバイスを選択するかを選択できます。 プロセスを完了し、デバイスに軽減策を適用するには、[ **軽減策の作成] アクション** を選択します。

:::image type="content" source="images/mitigation_options.png" alt-text="CVE-2021-44228 の軽減策オプション" lightbox="images/mitigation_options.png":::

### <a name="mitigation-status"></a>軽減策の状態

軽減状態は、JDNI ルックアップを無効にする回避策の軽減策がデバイスに適用されているかどうかを示します。 影響を受ける各デバイスの軽減策の状態は、[公開デバイス] タブで確認できます。 これは、軽減状態に基づいてデバイスの軽減策や修正プログラムの適用に優先順位を付けるのに役立ちます。

:::image type="content" source="images/mitigation_status.png" alt-text="考えられる軽減策の状態" lightbox="/mitigation_status.png":::

次の表に、潜在的な軽減策の状態を示します。

| 軽減策の状態 | 説明 |
|:---|:---|
| 適用される回避策 | _Windows_: LOG4J_FORMAT_MSG_NO_LOOKUPS環境変数は、最新のデバイスの再起動前に観察されました。 <br/><br/> _Linux + macOS_: 実行中のすべてのプロセスは、環境変数にLOG4J_FORMAT_MSG_NO_LOOKUPS=true を持ちます。 |
| 再起動中の回避策 | LOG4J_FORMAT_MSG_NO_LOOKUPS環境変数は設定されていますが、次の再起動は検出されません。 |
| 未適用 | _Windows_: LOG4J_FORMAT_MSG_NO_LOOKUPS環境変数は観察されませんでした。 <br/><br/> _Linux + macOS_: 実行中のプロセスの環境変数にLOG4J_FORMAT_MSG_NO_LOOKUPS=true というわけではありません。デバイスには軽減アクションが適用されませんでした。 |
| 部分的に軽減 | _Linux + macOS_: 軽減アクションはデバイスに適用されましたが、実行中のプロセスの環境変数にLOG4J_FORMAT_MSG_NO_LOOKUPS=true というわけではありません。 |
|該当なし | 軽減策のバージョン範囲にない脆弱なファイルを持つデバイス。 |
|不明 | 現時点では、軽減策の状態を特定できませんでした。 |

> [!NOTE]
> デバイスの更新された軽減状態が反映されるまでに数時間かかる場合があります。

### <a name="revert-mitigations-applied-for-the-log4shell-vulnerability"></a>Log4Shell の脆弱性に適用された軽減策を元に戻す

軽減策を元に戻す必要がある場合は、次の手順に従います。

**_Windowsの場合:_**

1. 管理者特権の PowerShell ウィンドウを開く
2. 次のコマンドを実行します。

 ```Powershell
   [Environment]::SetEnvironmentVariable("LOG4J\_FORMAT\_MSG\_NO\_LOOKUPS", $null,[EnvironmentVariableTarget]::Machine)
```

この変更は、デバイスの再起動後に有効になります。

**_Linux の場合:_**

1. ファイル /etc/environment を開き、行 LOG4JFORMATMSGNOLOOKUPS\_\_\_\_=true を削除します
2. ファイル /etc/systemd/system.conf.d/log4jdisablejndilookups.conf\_\_\_ を削除します
3. ファイル /etc/systemd/user.conf.d/log4jdisablejndilookups.conf\_\_\_ を削除します

この変更は、デバイスの再起動後に有効になります。

**_macOS の場合:_**

ファイル setenv を削除します。LOG4JFORMATMSGNOLOOKUPS.plist\_\_\_\_ を次のフォルダーから取得します。

  - */Library/LaunchDaemons/*
  - */Library/LaunchAgents/*
  - */Users/\[username\]/Library/LaunchAgents/ - すべてのユーザー*

この変更は、デバイスの再起動後に有効になります。

### <a name="apache-log4j-security-recommendations"></a>Apache Log4j のセキュリティに関する推奨事項

Apache log4j に関連するアクティブなセキュリティ推奨事項を表示するには、脆弱性の詳細ページから [ **セキュリティの推奨事項** ] タブを選択します。 この例では、 **Apache Log4j の更新** を選択すると、別のポップアップに詳細情報が表示されます。

:::image type="content" source="images/update_apache_log4j.png" alt-text="apache log4j のセキュリティに関する推奨事項を更新する" lightbox="images/update_apache_log4j.png":::

[ **修復の要求]** を選択して修復要求を作成します。

## <a name="explore-the-vulnerability-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで脆弱性を調べる

公開されたデバイス、ファイル、ソフトウェアが見つかったら、Microsoft 365 Defender ポータルで次のエクスペリエンスを通じて関連情報も伝達されます。

### <a name="security-recommendations"></a>セキュリティに関する推奨事項

**CVE-2021-44228** を検索して、Log4Shell の脆弱性に対処するセキュリティに関する推奨事項を確認します。

:::image type="content" source="images/security_recommendations_log4j.png" alt-text="セキュリティの推奨事項ページの log4j の脆弱性" lightbox="images/security_recommendations_log4j.png":::

### <a name="software-inventory"></a>ソフトウェア インベントリ

 ソフトウェア インベントリ ページで **CVE-2021-44228** を検索して、Log4j ソフトウェアのインストールと公開に関する詳細を確認します。

:::image type="content" source="images/software_inventory_log4j.png" alt-text="ソフトウェア インベントリ ページの log4j の脆弱性" lightbox="images/software_inventory_log4j.png":::

### <a name="weaknesses"></a>弱点

[弱点] ページで **CVE-2021-44228** を検索し、Log4Shell の脆弱性に関する情報を確認します。

:::image type="content" source="images/weaknesses_log4j.png" alt-text="弱点ページの log4j の脆弱性" lightbox="images/weaknesses_log4j.png":::

## <a name="use-advanced-hunting"></a>高度なハンティングを使用する

次の高度なハンティング クエリを使用して、デバイスにインストールされているソフトウェアの脆弱性を特定できます。

 ```text
    DeviceTvmSoftwareVulnerabilities
    | where CveId in ("CVE-2021-44228", "CVE-2021-45046")
 ```

次の高度なハンティング クエリを使用して、デバイスにインストールされているソフトウェアの脆弱性を特定し、ディスクからファイル レベルの結果を表示できます。

 ```text
    DeviceTvmSoftwareEvidenceBeta
    | mv-expand DiskPaths
    | where DiskPaths contains "log4j"
    | project DeviceId, SoftwareName, SoftwareVendor, SoftwareVersion, DiskPaths
 ```

## <a name="related-articles"></a>関連記事

- [脅威と脆弱性の管理の概要](http://next-gen-threat-and-vuln-mgt.md)
- [セキュリティに関する推奨事項](tvm-security-recommendation.md)