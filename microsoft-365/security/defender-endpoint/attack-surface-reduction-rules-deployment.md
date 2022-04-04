---
title: ASR ルールの展開の前提条件
description: 攻撃表面縮小 (ASR) ルールの展開に関する概要と前提条件のガイダンスを提供します。
keywords: 攻撃表面の縮小ルールの展開、ASR の展開、asr ルールの有効化、ASR の構成、ホスト侵入防止システム、保護ルール、悪用防止ルール、感染防止ルール、Microsoft Defender for Endpoint、ASR ルールの構成
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
ms.openlocfilehash: 4703867449877a35d6621b76072b9420a0cdbdec
ms.sourcegitcommit: 0ae89b71b202aceabd5061f0d5b46d030d93e931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "64520553"
---
# <a name="asr-rules-deployment-prerequisites"></a>ASR ルールの展開の前提条件

## <a name="before-you-begin"></a>はじめに

攻撃表面は、組織がサイバー脅威や攻撃に対して脆弱なすべての場所です。 組織の攻撃表面には、攻撃者が組織のデバイスやネットワークを侵害する可能性があるすべての場所が含まれています。 攻撃の表面を減らすことは、組織のデバイスとネットワークを保護する手段であり、攻撃方法が少ない攻撃者を残します。 攻撃表面の縮小 (ASR) ルールを構成すると、Microsoft Defender for Endpointに見つかる多くのセキュリティ機能の 1 つが役立ちます。

ASR ルールは、次のような特定のソフトウェア動作を対象とします。

- ファイルのダウンロードまたは実行を試みる実行可能ファイルとスクリプトの起動
- 難読化されたスクリプトまたはその他の疑わしいスクリプトを実行する
- 通常の日次作業中にアプリが通常は発生しない動作

異なる攻撃表面を減らすことで、攻撃が最初に起こらされるのを防ぐのに役立ちます。

最初の準備では、配置するシステムの機能を理解する必要があります。 この機能を理解すると、組織を保護するために最も重要な ASR ルールを特定するのに役立ちます。 さらに、ASR 展開の準備に参加する必要があるいくつかの前提条件があります。

>[!IMPORTANT]
>このガイドでは、ASR ルールを構成する方法を決定するのに役立つ画像と例を示します。これらのイメージと例は、環境に最適な構成オプションを反映していない可能性があります。

開始する前に、「 [攻撃表面](overview-attack-surface-reduction.md)の縮小の概要」と「 [Demystifying Attack Surface Reduction rules - Part 1 for foundational](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) information」を参照してください。 カバレッジの領域と潜在的な影響を理解するには、ASR ルールの現在のセットについて理解してください。「攻撃 [表面の縮小ルールリファレンス」を参照してください](attack-surface-reduction-rules-reference.md)。  ASR ルール セットについて理解している間は、ルールごとの GUID マッピングに注意してください。「 [ASR ルールと GUID マトリックス」を参照してください](attack-surface-reduction-rules-reference.md#asr-rules-and-guids-matrix)。

ASR ルールは、攻撃表面の縮小機能の 1 つの機能にMicrosoft Defender for Endpoint。 このドキュメントでは、人間が操作するランサムウェアなどの高度な脅威を阻止するために、ASR ルールを効果的に展開する方法について詳しく説明します。  

### <a name="rules-by-category"></a>カテゴリ別のルール

「攻撃表面の[](attack-surface-reduction.md)縮小ルールを使用してマルウェアの感染を防止する」で説明されている通り、MDE 内には複数の攻撃表面縮小ルールが含め、組織を保護できます。 カテゴリ別に分類されるルールを次に示します。

<br/>

| 多態性の脅威 | 横方向の移動&資格情報の盗難 | 生産性向上アプリのルール |  電子メール ルール | スクリプト ルール | その他のルール |
|:---|:---|:---|:---|:---|:---|
| 有病率 (1000 台のコンピューター)、年齢 (24 時間)、または信頼できるリスト条件を満たしない限り、実行可能ファイルの実行をブロックする | PSExec および WMI コマンドから発生するプロセス作成をブロックする | 実行可能Officeアプリの作成をブロックする | メール クライアントと Web メールから実行可能なコンテンツをブロックする | 難読化された JS/VBS/PS/マクロ コードをブロックする | 悪用された脆弱な署名済みドライバーの悪用をブロック <sup>する [[1](#fn1)]<sup></sup>  |
| USB から実行される信頼されていないプロセスと署名されていないプロセスをブロックする | ローカル セキュリティ機関サブシステムからの資格情報のWindowsをブロックする (lsass.exe)<sup>[[2](#fn1)]<sup></sup>   | アプリOffice子プロセスの作成をブロックする |  通信アプリケーションOffice子プロセスの作成のみをブロックする | JS/VBS のダウンロード済み実行可能コンテンツの起動をブロックする | |
| ランサムウェアに対する高度な保護の使用 | WMI イベント サブスクリプションによる永続化のブロック | アプリOffice他のプロセスへのコードの挿入をブロックする | 通信Office子プロセスの作成をブロックする | | |
| | | Adobe Reader の子プロセスの作成をブロックする | | | |

(<a id="fn1">1</a>) _脆弱_ な署名済みドライバーの悪用をブロックする機能は、MEM Endpoint セキュリティでは現在利用できません。 このルールは、 [MEM OMA-URI を使用して構成できます](enable-attack-surface-reduction.md#mem)。

(<a id="fn1">2</a>) 一部の ASR ルールではかなりのノイズが発生しますが、機能はブロックできません。 たとえば、Chrome を更新する場合。Chrome はユーザーにlsass.exe。パスワードはデバイスの lsass に保存されます。 ただし、Chrome はローカル デバイスにアクセスlsass.exe。 lsass へのアクセスをブロックするルールを有効にした場合、多くのイベントが生成されます。 これらのイベントは、ソフトウェア更新プロセスがユーザーにアクセスしないので、lsass.exe。 このルールを有効にすると、Chrome の更新プログラムによる lsass へのアクセスはブロックされますが、Chrome の更新はブロックされます。これは、ユーザーに対して不要な呼び出しを行う他のアプリケーションlsass.exe。 _lsass ルールへのブロック アクセスは、lsass_ への不要な呼び出しをブロックしますが、アプリケーションの実行をブロックしません。

### <a name="infrastructure-requirements"></a>インフラストラクチャの要件

ASR ルールを実装する複数の方法が可能ですが、このガイドは次のインフラストラクチャに基づいて作成されます。

- Azure Active Directory
- Microsoft Endpoint Management (MEM)
- Windows 10デバイスとWindows 11デバイス
- Microsoft Defender for Endpoint E5 ライセンスまたは e5 Windowsライセンス

ASR ルールとレポートをフルに活用するには、E5 または E5 ライセンス、および A5 Microsoft 365 DefenderをWindowsすることをお勧めします。 詳細については、「最小[要件」を参照](minimum-requirements.md)Microsoft Defender for Endpoint。

>[!Note]
>ASR ルールを構成するには、複数の方法があります。 ASR ルールは、Microsoft エンドポイント マネージャー(MEM)、PowerShell、グループ ポリシー、Microsoft System Center Configuration Manager (SCCM)、MEM OMA-URI を使用して構成できます。
>インフラストラクチャ _要件 (上記_) に記載されているインフラストラクチャ構成とは異なるインフラストラクチャ構成を使用している場合は、他の構成を使用して攻撃表面の縮小ルールを展開する方法の [](enable-attack-surface-reduction.md)詳細については、「攻撃表面の縮小ルールを有効にする」を参照してください。  

### <a name="asr-rules-dependencies"></a>ASR ルールの依存関係

Microsoft Defender ウイルス対策プライマリ ウイルス対策ソリューションとして有効および構成する必要があります。次のモードである必要があります。

- プライマリ ウイルス対策/マルウェア対策ソリューション  
- 状態: アクティブ モード

Microsoft Defender ウイルス対策モードを使用しない必要があります。

- パッシブ
- ブロック モードでのエンドポイントの検出と応答 (EDR) のパッシブ モード
- 限られた定期的なスキャン (LPS)
- Off

「クラウド[配信の保護と保護」を参照Microsoft Defender ウイルス対策](cloud-protection-microsoft-defender-antivirus.md)。

### <a name="cloud-protection-maps-must-be-enabled"></a>クラウド保護 (MAPS) を有効にする必要があります

Microsoft Defender ウイルス対策 Microsoft クラウド サービスとシームレスに連携します。 Microsoft Advanced Protection Service (MAPS) とも呼ばれるこれらのクラウド保護サービスは、標準のリアルタイム保護を強化し、間違いなく最高のウイルス対策防御を提供します。 クラウド保護は、マルウェアからの侵害や ASR ルールの重要なコンポーネントを防止するために重要です。
[クラウドで配信される保護をオンMicrosoft Defender ウイルス対策](enable-cloud-protection-microsoft-defender-antivirus.md)。

### <a name="microsoft-defender-antivirus-components-must-be-current-versions"></a>Microsoft Defender ウイルス対策コンポーネントは現在のバージョンである必要があります

次のMicrosoft Defender ウイルス対策コンポーネント バージョンは、現在利用可能なバージョンより 2 つ以上古いバージョンである必要があります。

- **Microsoft Defender ウイルス対策プラットフォーム更新プログラムのバージョン** - Microsoft Defender ウイルス対策は毎月更新されます。
- **Microsoft Defender ウイルス対策エンジンのバージョン** - Microsoft Defender ウイルス対策は毎月更新されます。
- **Microsoft Defender ウイルス対策インテリジェンス** - Microsoft は、Microsoft Defender のセキュリティ インテリジェンス (定義と署名とも呼ばれる) を継続的に更新して、最新の脅威に対処し、検出ロジックを絞り込む。

最新のMicrosoft Defender ウイルス対策を維持すると、ASR ルールの誤検知結果が減少し、検出機能Microsoft Defender ウイルス対策向上します。 現在のバージョンと異なるコンポーネントを更新する方法の詳細については、Microsoft Defender ウイルス対策サポートMicrosoft Defender ウイルス対策[覧ください](manage-updates-baselines-microsoft-defender-antivirus.md)。

### <a name="caveat"></a>注意点

一部のルールは、署名されていない、内部的に開発されたアプリケーションとスクリプトの使用率が高い場合、うまく動作しません。 コード署名が適用されない場合は、ASR ルールを展開する方が困難です。

## <a name="asr-rules-deployment-steps"></a>ASR ルールの展開手順

ビジネスラインの運用に影響を与える可能性のある新しい大規模な実装と同様に、計画と実装では計画的な方法が重要です。 ASR ルールがマルウェアを防止する強力な機能を備えるので、独自の顧客ワークフローに最適な動作を実現するには、これらのルールの慎重な計画と展開が必要です。 環境で作業するには、ASR ルールを慎重に計画、テスト、実装、運用する必要があります。  

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-deployment-phases.png" alt-text="ASR ルールの展開フェーズ" lightbox="images/asr-rules-deployment-phases.png":::

>[!Note]
>Microsoft 以外の HIPS を使用し、Microsoft Defender for Endpoint 攻撃表面の縮小ルールに移行しているお客様の場合:監査モードからブロック モードに移行するまで、ASR ルールの展開を使用して HIPS ソリューションをサイド バイ サイドで実行する必要があります。 除外の推奨事項については、サードパーティのウイルス対策ベンダーに問い合う必要があります。  

## <a name="additional-topics-in-this-deployment-collection"></a>この展開コレクションのその他のトピック

[フェーズ 1: 計画](attack-surface-reduction-rules-deployment-plan.md)

[フェーズ 2: テスト](attack-surface-reduction-rules-deployment-test.md)

[フェーズ 3: 実装](attack-surface-reduction-rules-deployment-implement.md)

[フェーズ 4: 運用化](attack-surface-reduction-rules-deployment-operationalize.md)

## <a name="reference"></a>関連情報

### <a name="blogs"></a>ブログ

[攻撃表面の縮小ルールの定義 - パート 1](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)

[攻撃表面の縮小ルールの定義 - パート 2](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-2/ba-p/1326565)

[攻撃表面の縮小ルールの定義 - パート 3](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)

[攻撃表面の縮小ルールの定義 - パート 4](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-4/ba-p/1384425)

### <a name="asr-collection"></a>ASR コレクション

[攻撃面の減少の概要](overview-attack-surface-reduction.md)

[マルウェア感染を防ぐために攻撃面の減少ルールを使用する](attack-surface-reduction.md)

[攻撃面の減少ルールを有効にする](enable-attack-surface-reduction.md)

[攻撃表面の縮小ルールのリファレンス](attack-surface-reduction-rules-reference.md)

[攻撃面の減少の FAQ](attack-surface-reduction-faq.yml)

### <a name="microsoft-defender"></a>Microsoft Defender

[Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)

[クラウド配信保護と Microsoft Defender ウイルス対策](cloud-protection-microsoft-defender-antivirus.md)

[クラウドで配信される保護を有効 Microsoft Defender ウイルス対策にする](enable-cloud-protection-microsoft-defender-antivirus.md)

[拡張機能、名前、または場所に基づいて除外を構成および検証する](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

[Microsoft Defender ウイルス対策プラットフォームのサポート](manage-updates-baselines-microsoft-defender-antivirus.md)

[管理センターの在庫Microsoft 365 Apps概要](/deployoffice/admincenter/inventory)

[ユーザーの展開計画を作成Windows](/windows/deployment/update/create-deployment-plan)

[役割ベースのアクセス制御 (RBAC) とスコープ タグを使用して、ネットワーク内の分散 IT にIntune](/mem/intune/fundamentals/scope-tags)

[Microsoft Intune でのデバイス プロファイルの割り当て](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)

### <a name="management-sites"></a>管理サイト

[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com/#home)

[攻撃面の減少](https://security.microsoft.com/asr?viewid=detections)

[ASR ルール構成](https://security.microsoft.com/asr?viewid=configuration)

[ASR ルールの除外](https://security.microsoft.com/asr?viewid=exclusions)
