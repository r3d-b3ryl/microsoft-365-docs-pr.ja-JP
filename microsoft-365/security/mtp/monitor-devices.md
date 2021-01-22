---
title: デバイス監視&レポート - セキュリティ センター
description: デバイスをセキュリティで保護し、最新の状態に保ち、組織内の潜在的な脅威を特定する方法について説明します。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティ センター, 監視, レポート, デバイス
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930500"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターでのデバイスの監視とレポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


デバイスをセキュリティで保護し、最新の状態に保ち、Microsoft 365 セキュリティ センターで潜在的な脅威を特定します。

## <a name="view-device-alerts"></a>デバイスのアラートを表示する

Microsoft Defender for Endpoint (E5 ライセンスで利用可能) から、デバイス上の侵害アクティビティや他の脅威に関する最新のアラートを取得します。 Microsoft 365 セキュリティ センターでは、お好みのワークフローを使用して、これらのアラートを高いレベルで効果的に監視します。

### <a name="monitor-high-impact-alerts"></a>影響の大きなアラートを監視する

各 Microsoft Defender for Endpoint アラートには、対応する重大度 (高、中、低、または情報) があります。 これは、無人のままにしておくとネットワークに影響を与える可能性を示します。  

デバイスアラート **の重大度カードを使って** 、特に重要度が高く、直ちに応答が必要になる可能性があるアラートに重点を置く。 このカードから、Microsoft Defender セキュリティ センター ポータルで詳細を表示できます。

![デバイスアラートの重大度カード](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>アラートのソースを理解する

Microsoft Defender for Endpoint は、広範なセキュリティ センサーとインテリジェンス ソースからのデータを利用して、アラートを生成します。 たとえば、Microsoft Defender ウイルス対策とサード パーティのマルウェア対策からの検出情報を使用できます。 また、Web サービス API を通じて提供される独自のカスタム脅威インテリジェンスを使用することもできます。

デバイス **アラート検出ソース カード** には、ソース別のアラートの配布が表示されます。 特定のソース、特にカスタム ソースに関連するアクティビティを追跡します。 また、このカードを使用して、悪意のあるアクティビティやコンポーネントを自動的にブロックするように構成されていないセンサーからのアラートに焦点を当てすることもできます。

![デバイスアラート検出ソース カード](../../media/device-alert-detection-sources.png)

このカードから、Microsoft Defender セキュリティ センター ポータルで詳細を表示できます。

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>アラートをトリガーする脅威の種類を理解する

Microsoft Defender for Endpoint は、各アラートを、攻撃チェーンまたは脅威コンポーネントの種類の特定のステージを表すカテゴリに分類します。 たとえば、検出された脅威アクティビティは、ネットワーク上の他のデバイスに到達しようとしたかどうかを示すために、"横方向の動き" として分類できます。 このアクティビティは、攻撃者が最初の足がかりを獲得した後に発生する可能性があります。 検出された脅威コンポーネントは、広範にマルウェアとして分類される場合や、具体的には特定の脅威の種類として分類される場合があります。 具体的には、ランサムウェア、資格情報の盗用、その他の種類の悪意のあるソフトウェアや不要なソフトウェアが含まれます。

デバイス **の脅威カテゴリ カード** には、これらのカテゴリへのアラートの分布が表示されます。 この情報を使用して、資格情報の盗難の試みなど、通常はソーシャル エンジニアリングの試みよりも大きな影響を与える脅威アクティビティを特定します。 ランサムウェアなどの潜在的な破壊的な脅威を監視できます。

![デバイスの脅威カテゴリ カード](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>アクティブなアラートを監視する

デバイス **アラートステータス カード** は、解決されていないアラートの数を示し、注意が必要な場合があります。 このカードから、Microsoft Defender セキュリティ センター ポータルで詳細を表示できます。

![デバイスアラートの状態カード](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>解決済みアラートの分類を監視する

Microsoft Defender for Endpoint の警告を解決する際、セキュリティ スタッフはアラートが次のように検証されているかどうかを指定できます。

* 実際の侵害アクティビティまたは脅威コンポーネントを識別する真のアラート
* 通常のアクティビティを誤って検出した誤ったアラート

デバイス **アラート分類カードには** 、解決済みアラートが true アラートと False アラートの分類の 2 つが表示されます。 このカードから、Microsoft Defender セキュリティ センター ポータルで詳細を表示できます。

注: 場合によっては、特定のアラートで分類情報を使用できない場合があります。

![デバイスアラート分類カード](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>解決済みアラートの判断を監視する

解決時にアラートが正しいか偽かを分類すると共に、セキュリティ スタッフが判断を下す場合があります。 判定は、アラートの検証中に検出された通常または悪意のあるアクティビティの種類を示します。

デバイス **アラート判定カードには** 、各アラートに対して提供された判定が表示されます。

* **APT**: 検出されたアクティビティまたは脅威コンポーネントが、影響を受けるネットワークの足がかりを得るために設計された高度な侵害の一部であることを示す、持続的な脅威  
* **マルウェア**: 悪意のあるファイルまたはコード
* **セキュリティ担当者**: セキュリティ スタッフが実行する通常のアクティビティ
* **セキュリティ テスト**: 実際の脅威をシミュレートし、セキュリティ センサーをトリガーしてアラートを生成すると予想されるアクティビティまたはコンポーネント
* **望ましくないソフトウェア**: 悪意のあると見なされないアプリや他のソフトウェア。ポリシーや許容される使用基準に違反する
* **その** 他 : 指定された種類に該当しないその他の判断

このカードから、Microsoft Defender セキュリティ センターで詳細を表示できます。

![デバイスアラート判定カード](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>どのデバイスが危険にさらされているのかについて理解する

**デバイス保護は** 、デバイスのリスク レベルを示します。 リスク レベルは、デバイス上のアラートの種類や重要度などの要因に基づいて決定されます。

![デバイス保護カード](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Intune で管理されているデバイスの状態を監視およびレポートする

次のレポートには、Intune に登録されているデバイスからのデータが含まれます。 登録解除されたデバイスからのデータは含まれません。 これらのカードを表示できるのはグローバル管理者のみです。

Intune に登録されているデバイス データには、次が含まれます。

* デバイスのポリシー準拠
* アクティブなマルウェアを持つデバイス
* デバイス上のマルウェアの種類
* デバイス上のマルウェア
* マルウェアが検出されたデバイス
* マルウェアが検出されたユーザー

### <a name="monitor-device-compliance"></a>デバイスのコンプライアンスを監視する

**デバイス コンプライアンスは** 、Intune に登録されているデバイスが構成ポリシーに準拠しているデバイスの数を示します。

![デバイス コンプライアンス カード](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>マルウェアが検出されたデバイスを検出する

**デバイスのマルウェア検出** では、完全に解決されていないマルウェアが Intune に登録されたデバイスの数を提供します。 解決策がないのは、保留中のアクション、再起動、フル スキャン、手動ユーザー操作、または修復アクションが正常に完了しなかった場合です。

![デバイス マルウェア検出カード](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>検出されたマルウェアの種類を理解する

**デバイス上のマルウェアの種類には** 、Intune に登録されているデバイスで検出されたさまざまな種類のマルウェアが表示されます。 Microsoft 365 セキュリティ センターでは、それぞれの種類を調査できます。

![デバイス カードのマルウェアの種類](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>デバイスで検出された特定のマルウェアについて理解する

**デバイス上のマルウェア** は、デバイスで検出された特定のマルウェアの一覧を提供します。

![デバイス カード上のマルウェア](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>マルウェアが最も多いデバイスを理解する

**マルウェアが検出されたデバイスは、** 最もマルウェアが検出されたデバイスを示します。 Microsoft 365 セキュリティ センターでは、マルウェアがアクティブかどうか、デバイスを使用するユーザー、Intune での管理状態を調査できます。

![マルウェア検出カードを含むデバイス](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>マルウェアが最も多いデバイスを持つユーザーを把握する

**マルウェアが検出されたユーザーは** 、最もマルウェアが検出されたデバイスを持つユーザーを表示します。 Microsoft 365 セキュリティ センターでは、各ユーザーに割り当てられているデバイスの数と、各デバイスとマルウェアの種類に関する詳細を確認できます。

![マルウェア検出カードを持つユーザー](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a>攻撃表面の縮小ルールの展開と検出を監視および管理する

[攻撃表面の縮小 (ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) ルールは、悪用を求めるマルウェアがデバイスに感染するために通常使用するアクションやアプリを防止するのに役立ちます。 このようなルールによって、実行可能ファイルの実行を許可するタイミングと方法を制御します。 たとえば、JavaScript や VBScript がダウンロードした実行可能ファイルを開始することを禁止したり、Office マクロからの Win32 API 呼び出しをブロックしたり、USB ドライブから実行するプロセスをブロックしたりできます。

![攻撃表面の縮小カード](../../media/attack-surface-reduction-rules.png)

**[攻撃面の減少ルール]** カードには、デバイス全体に配置するルールの概要が示されます。

カードの上部バーには、次の配置モードになっているデバイスの合計数が表示されます。

* **ブロック モード**: 検出されたアクティビティをブロックするように少なくとも 1 つのルールが構成されているデバイス
* **監査モード**: 検出されたアクティビティをブロックするルールが設定されているのに、検出されたアクティビティを監査するルールが少なくとも 1 つ設定されているデバイス  
* **オフ**: すべての ASR ルールがオフになっているデバイス

このカードの下側には、デバイス全体のルール別の設定が表示されます。 各バーは、ブロック、監査検出、またはルールが完全にオフに設定されているデバイスの数を示します。

### <a name="view-asr-detections"></a>ASR 検出の表示

ネットワーク内の ASR ルールの検出に関する詳細情報を表示するには、攻撃表面の縮小ルール カードで [検出の表示 **] を選択** します。 詳細 **レポート ページ** の [検出] タブが開きます。

![[検出] タブ](../../media/detections-tab.png)

ページの上部にあるグラフには、ブロックまたは監査された検出を、時間のときどき積み重ねたった検出が表示されます。 下部の表は、最近の検出のリストです。 表に示された次の情報を使用して、検出の種類を理解します。

* **検出されたファイル**: 攻撃の疑いのあるアクティビティをトリガーした内容のファイル (通常はスクリプトまたはドキュメント)
* **Rule**: ルールがキャッチするように設計されている攻撃アクティビティを説明する名前。 既存の ASR ルールの読み取り
* **ソース アプリ**: 攻撃の疑いのあるアクティビティをトリガーするコンテンツを読み込んだ、または実行したアプリケーション。 Web ブラウザー、Office アプリケーション、PowerShell などのシステム ツールなど、正当なアプリケーションである可能性があります。
* **発行** 元: ソース アプリをリリースしたベンダー

### <a name="review-device-asr-rule-settings"></a>デバイス ASR ルールの設定を確認する

[攻撃表面 **の縮小ルール]** レポート ページで、[構成] タブに移動して、個々のデバイスのルール設定を確認します。 デバイスを選択すると、各ルールがブロック モード、監査モード、または完全にオフになっているかどうかに関する詳細情報が表示されます。

![[構成] タブ](../../media/configuration-tab.png)

Microsoft Intune は、ASR ルールの管理機能を提供します。 設定を更新する場合は、タブの[デバイスの構成] の [開始] を選択して、Intune でデバイス管理を開きます。

### <a name="exclude-files-from-asr-rules"></a>ASR ルールからファイルを除外する

Microsoft 365 セキュリティ センターは、攻撃[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules)表面の縮小ルールによって、検出から除外する可能性があるファイルの名前を収集します。 ファイルを除外することで、誤検知の検出を減らし、攻撃表面の縮小ルールをブロック モードでより自信を持って展開できます。

除外は Microsoft Intune で管理されますが、Microsoft 365 セキュリティ センターには、ファイルを理解するのに役立つ分析ツールが提供されています。 除外するファイルの収集を開始するには、[攻撃表面の縮小ルール] レポート ページの [除外の追加 **] タブに** 移動します。

>[!NOTE]  
>このツールは、すべての攻撃表面の縮小ルールによる検出を分析しますが、除外 [をサポートするルールは一部のみです](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)。

![[除外の追加] タブ](../../media/add-exclusions-tab.png)

次の表に、攻撃表面の縮小ルールによって検出されたファイル名の一覧を示します。 ファイルを選択すると、除外の影響を確認できます。

* 検出数の少ない数
* 検出を報告するデバイスの数

除外する完全なパスを持つ、選択したファイルの一覧を取得するには、[除外パスの取得 **] を選択します**。

ASR ルールのログ。Windows ローカル セキュリティ機関サブシステム **(lsass.exe)** からの資格情報の盗用をブロックし、ソース アプリを取得 **lsass.exe。** 通常のシステム ファイルですが、検出されたファイルとしてキャプチャされます。 その結果、生成された除外パスの一覧にこのファイルが含まれます。 lsass.exeではなく、このルールをトリガーしたファイルを除外するには、検出されたファイルの代わりにソース アプリのパスを使用します。

ソース アプリを見つけるには、この[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)特定のルールに対して次の高度な検索クエリを実行します (ルール ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 によって識別されます)。

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>除外するファイルを確認する

ASR からファイルを除外する前に、ファイルを検査して、実際に悪意のあるファイルではないかどうかを判断することをお勧めします。

ファイルを確認するには、Microsoft Defender セキュリティ センター [の](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) ファイル情報ページを使います。 このページには、確認率情報と VirusTotal ウイルス検出率が表示されます。 ページを使用して、詳細分析のためにファイルを送信することもできます。

Microsoft Defender セキュリティ センターで検出されたファイルを見つけるには、次の高度な捜索クエリを使用してすべての ASR 検出を検索します。

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

結果で **SHA1** または **InitiatingProcessSHA1** を使用して、Microsoft Defender セキュリティ センターのユニバーサル検索バーを使用してファイルを検索します。
