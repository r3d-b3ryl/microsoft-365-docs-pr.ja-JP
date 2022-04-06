---
title: ASR ルールの展開の前提条件
description: 攻撃表面縮小 (ASR) ルールの展開に関する概要と前提条件のガイダンスについて説明します。
keywords: 攻撃表面の縮小ルールの展開、ASR 展開、ASR の有効化、ASR の構成、ホスト侵入防止システム、保護規則、悪用防止ルール、悪用防止ルール、悪用防止ルール、感染防止ルール、Microsoft Defender for Endpoint、ASR 規則の構成
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection:
- m365solution-scenario
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: 0180bfcef9d478dcf8e334a180ea3df993585e00
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666418"
---
# <a name="asr-rules-deployment-prerequisites"></a>ASR ルールの展開の前提条件

## <a name="before-you-begin"></a>はじめに

攻撃面は、組織がサイバー脅威や攻撃に対して脆弱なすべての場所です。 組織の攻撃面には、攻撃者が組織のデバイスまたはネットワークを侵害する可能性があるすべての場所が含まれます。 攻撃対象を減らすことは、組織のデバイスとネットワークを保護することを意味します。これにより、攻撃者の攻撃方法が少なくなります。 Microsoft Defender for Endpointで見つかった多くのセキュリティ機能の 1 つである攻撃表面縮小 (ASR) ルールの構成が役立ちます。

ASR ルールは、次のような特定のソフトウェア動作を対象とします。

- ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトの起動
- 難読化された、またはその他の疑わしいスクリプトの実行
- 通常の日常的な作業中にアプリが通常発生しない動作

さまざまな攻撃面を減らすことで、最初に攻撃が発生するのを防ぐのに役立ちます。

最初の準備では、配置するシステムの機能を理解することが重要です。 この機能を理解すると、組織を保護するために最も重要な ASR 規則を判断するのに役立ちます。 また、ASR デプロイの準備に必要な前提条件がいくつかあります。

>[!IMPORTANT]
>このガイドでは、ASR ルールを構成する方法を決定するのに役立つ画像と例を示します。これらのイメージと例は、環境に最適な構成オプションを反映していない可能性があります。

開始する前に、基本的な情報については、 [攻撃表面の縮小の概要](overview-attack-surface-reduction.md)と [攻撃面の縮小ルールの概要 (パート 1](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) ) を参照してください。 カバレッジの領域と潜在的な影響を理解するには、現在の ASR ルールのセットについて理解します。 [「攻撃面の縮小ルールのリファレンス」を参照してください](attack-surface-reduction-rules-reference.md)。  ASR ルール セットについて理解している間は、ルールごとの GUID マッピングに注意してください。参照: [ASR ルールと GUID マトリックス](attack-surface-reduction-rules-reference.md#asr-rules-and-guids-matrix)。

ASR ルールは、Microsoft Defender for Endpoint内の攻撃面の縮小機能の 1 つの機能にすぎません。 このドキュメントでは、人間が操作するランサムウェアなどの高度な脅威を阻止するために ASR ルールを効果的に展開する方法について詳しく説明します。  

### <a name="rules-by-category"></a>カテゴリ別のルール

[「マルウェア感染を防ぐために攻撃表面の縮小ルールを使用する](attack-surface-reduction.md)」で説明されているように、MDE 内には、組織を保護するために有効にできる複数の攻撃面縮小ルールがあります。 カテゴリ別に分けたルールを次に示します。

<br/>

| 多形の脅威 | 横移動&資格情報の盗難 | 生産性アプリのルール |  電子メール ルール | スクリプト ルール | その他のルール |
|:---|:---|:---|:---|:---|:---|
| 有病率 (1000 台のマシン)、年齢 (24 時間)、信頼できるリスト条件を満たしていない限り、実行可能ファイルの実行をブロックする | PSExec コマンドと WMI コマンドから生成されたプロセス作成をブロックする | アプリOffice実行可能コンテンツの作成をブロックする | 電子メール クライアントと webmail から実行可能コンテンツをブロックする | 難読化された JS/VBS/PS/マクロ コードをブロックする | 悪用された脆弱な署名されたドライバー <sup>の悪用をブロックする [[1](#fn1)]<sup></sup>  |
| USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする | Windowsローカル セキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)<sup>[[2](#fn1)]<sup></sup>   | Office アプリによる子プロセスの作成をブロックする |  通信アプリケーションOffice子プロセスの作成のみをブロックする | ダウンロードした実行可能コンテンツの起動から JS/VBS をブロックする | |
| ランサムウェアに対する高度な保護を使用する | WMI イベント サブスクリプションを使用して永続化をブロックする | Office アプリが他のプロセスにコードを挿入できないようにブロックする | 通信アプリOffice子プロセスの作成をブロックする | | |
| | | Adobe Reader による子プロセスの作成をブロックする | | | |

(<a id="fn1">1</a>) _悪用された脆弱な署名付きドライバーの悪用をブロック_ することは、MEM エンドポイント のセキュリティでは現在使用できません。 このルールは [、MEM OMA-URI を](enable-attack-surface-reduction.md#mem)使用して構成できます。

(<a id="fn1">2</a>) ASR ルールによっては、かなりのノイズが生成されますが、機能はブロックされません。 たとえば、Chrome を更新している場合は次のようになります。Chrome はlsass.exeにアクセスします。パスワードはデバイス上の lsass に格納されます。 ただし、Chrome がローカル デバイス lsass.exeにアクセスすることはできません。 ルールが lsass へのアクセスをブロックできるようにすると、多くのイベントが生成されます。 これらのイベントは、ソフトウェア更新プロセスがlsass.exeにアクセスしてはならないため、適切なイベントです。 このルールを有効にすると、Chrome の更新が lsass にアクセスできなくなりますが、Chrome の更新はブロックされません。これは、lsass.exeに対して不要な呼び出しを行う他のアプリケーションにも当てはまります。 _lsass ルールへのアクセスをブロックすると、lsass_ への不要な呼び出しはブロックされますが、アプリケーションの実行はブロックされません。

### <a name="infrastructure-requirements"></a>インフラストラクチャの要件

ASR ルールを実装する複数の方法は可能ですが、このガイドは次で構成されるインフラストラクチャに基づいています。

- Azure Active Directory
- Microsoft Endpoint Management (MEM)
- デバイスのWindows 10とWindows 11
- E5 または Windows E5 ライセンスをMicrosoft Defender for Endpointする

ASR ルールとレポートを最大限に活用するには、Microsoft 365 Defender E5 または Windows E5 ライセンスと A5 を使用することをお勧めします。 詳細情報: [Microsoft Defender for Endpointの最小要件](minimum-requirements.md)。

>[!Note]
>ASR ルールを構成するには、複数の方法があります。 ASR ルールは、Microsoft エンドポイント マネージャー (MEM)、PowerShell、グループ ポリシー、Microsoft System Center Configuration Manager (SCCM)、MEM OMA-URI を使用して構成できます。
>_インフラストラクチャ要件_ (上記) に記載されているものとは異なるインフラストラクチャ構成を使用している場合は、他の構成を使用して攻撃表面の縮小ルールを展開する方法について詳しくは、「[攻撃面の縮小ルールを有効にする」](enable-attack-surface-reduction.md)をご覧ください。  

### <a name="asr-rules-dependencies"></a>ASR ルールの依存関係

Microsoft Defender ウイルス対策は、プライマリウイルス対策ソリューションとして有効にし、構成する必要があり、次のモードである必要があります。

- プライマリ ウイルス対策/マルウェア対策ソリューション  
- 状態: アクティブ モード

Microsoft Defender ウイルス対策は、次のいずれかのモードにすることはできません。

- パッシブ
- ブロック モードでのエンドポイントの検出と応答 (EDR) を含むパッシブ モード
- 限られた定期的なスキャン (LPS)
- オフ

「[クラウド配信の保護とMicrosoft Defender ウイルス対策](cloud-protection-microsoft-defender-antivirus.md)」を参照してください。

### <a name="cloud-protection-maps-must-be-enabled"></a>Cloud Protection (MAPS) を有効にする必要があります

Microsoft Defender ウイルス対策は、Microsoft クラウド サービスとシームレスに連携します。 Microsoft Advanced Protection Service (MAPS) とも呼ばれるこれらのクラウド保護サービスは、標準のリアルタイム保護を強化し、間違いなく最高のウイルス対策防御を提供します。 マルウェアからの侵害や ASR ルールの重要なコンポーネントを防ぐには、クラウド保護が重要です。
[Microsoft Defender ウイルス対策でクラウド配信保護を有効にします](enable-cloud-protection-microsoft-defender-antivirus.md)。

### <a name="microsoft-defender-antivirus-components-must-be-current-versions"></a>Microsoft Defender ウイルス対策 コンポーネントは現在のバージョンである必要があります

次のMicrosoft Defender ウイルス対策 コンポーネント バージョンは、現在使用可能なバージョンより 2 つ以上古いバージョンにする必要があります。

- **Microsoft Defender ウイルス対策 プラットフォームの更新バージョン** - Microsoft Defender ウイルス対策 プラットフォームは毎月更新されます。
- **Microsoft Defender ウイルス対策 エンジンのバージョン** - Microsoft Defender ウイルス対策 エンジンは毎月更新されます。
- **Microsoft Defender ウイルス対策セキュリティ インテリジェンス** - Microsoft は、最新の脅威に対処し、検出ロジックを改善するために、Microsoft Defender セキュリティ インテリジェンス (定義と署名とも呼ばれます) を継続的に更新します。

Microsoft Defender ウイルス対策バージョンを最新の状態に保つことは、ASR ルールの誤検知の結果を減らし、Microsoft Defender ウイルス対策検出機能を向上させます。 現在のバージョンと、さまざまなMicrosoft Defender ウイルス対策 コンポーネントを更新する方法の詳細については、[プラットフォームのサポートMicrosoft Defender ウイルス対策](manage-updates-baselines-microsoft-defender-antivirus.md)参照してください。

### <a name="caveat"></a>警告

一部のルールは、署名されていない、内部的に開発されたアプリケーションとスクリプトの使用率が高い場合にうまく動作しません。 コード署名が適用されていない場合、ASR ルールをデプロイすることはより困難です。

## <a name="asr-rules-deployment-steps"></a>ASR ルールのデプロイ手順

基幹業務に影響を与える可能性のある新しい大規模な実装と同様に、計画と実装に方法的であることが重要です。 マルウェアを防止するための ASR ルールの強力な機能により、これらのルールを慎重に計画および展開して、一意の顧客ワークフローに最適に動作するようにする必要があります。 環境で作業するには、ASR ルールを慎重に計画、テスト、実装、運用する必要があります。  

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-deployment-phases.png" alt-text="ASR ルールのデプロイ フェーズ" lightbox="images/asr-rules-deployment-phases.png":::

>[!Note]
>Microsoft 以外の HIPS を使用していて、Microsoft Defender for Endpoint攻撃面の縮小ルールに移行しているお客様の場合:監査モードからブロック モードに移行するまで、ASR ルールの展開で HIPS ソリューションを並行して実行することをお客様に推奨します。 除外に関する推奨事項については、サード パーティのウイルス対策ベンダーに連絡する必要があることに注意してください。  

## <a name="additional-topics-in-this-deployment-collection"></a>このデプロイ コレクションのその他のトピック

[フェーズ 1: 計画](attack-surface-reduction-rules-deployment-plan.md)

[フェーズ 2: テスト](attack-surface-reduction-rules-deployment-test.md)

[フェーズ 3: 実装](attack-surface-reduction-rules-deployment-implement.md)

[フェーズ 4: 運用化](attack-surface-reduction-rules-deployment-operationalize.md)

## <a name="reference"></a>Reference

### <a name="blogs"></a>ブログ

[攻撃面の縮小ルールを解き放つ - パート 1](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)

[攻撃面の縮小ルールを解読する - パート 2](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-2/ba-p/1326565)

[攻撃面の縮小ルールをデミスティック化する - パート 3](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)

[攻撃面の縮小ルールを解き放つ - パート 4](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-4/ba-p/1384425)

### <a name="asr-collection"></a>ASR コレクション

[攻撃面の減少の概要](overview-attack-surface-reduction.md)

[マルウェア感染を防ぐために攻撃面の減少ルールを使用する](attack-surface-reduction.md)

[攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md)

[攻撃面の縮小ルールリファレンス](attack-surface-reduction-rules-reference.md)

[攻撃面の減少の FAQ](attack-surface-reduction-faq.yml)

### <a name="microsoft-defender"></a>Microsoft Defender

[Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)

[クラウド配信保護と Microsoft Defender ウイルス対策](cloud-protection-microsoft-defender-antivirus.md)

[Microsoft Defender ウイルス対策でクラウド配信保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)

[拡張機能、名前、または場所に基づいて除外を構成して検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

[Microsoft Defender ウイルス対策プラットフォームのサポート](manage-updates-baselines-microsoft-defender-antivirus.md)

[Microsoft 365 Apps管理センターのインベントリの概要](/deployoffice/admincenter/inventory)

[Windowsの展開計画を作成する](/windows/deployment/update/create-deployment-plan)

[Intuneで分散 IT にロールベースのアクセス制御 (RBAC) タグとスコープ タグを使用する](/mem/intune/fundamentals/scope-tags)

[Microsoft Intune でのデバイス プロファイルの割り当て](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)

### <a name="management-sites"></a>管理サイト

[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com/#home)

[攻撃面の減少](https://security.microsoft.com/asr?viewid=detections)

[ASR ルールの構成](https://security.microsoft.com/asr?viewid=configuration)

[ASR ルールの除外](https://security.microsoft.com/asr?viewid=exclusions)
