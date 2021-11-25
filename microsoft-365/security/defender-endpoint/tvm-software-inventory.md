---
title: ソフトウェア インベントリ (脅威と脆弱性の管理
description: Microsoft Defender for Endpoint のソフトウェア インベントリ ページ脅威と脆弱性の管理ソフトウェアで検出された弱点と脆弱性の数を示します。
keywords: 脅威と脆弱性の管理、Microsoft Defender for Endpoint、Microsoft Defender for Endpoint ソフトウェア インベントリ、Microsoft Defender for Endpoint Threat & 脆弱性の管理、Microsoft Defender for Endpoint Threat & 脆弱性の管理 ソフトウェア インベントリ、Microsoft Defender for Endpoint tvm ソフトウェア インベントリ、tvm ソフトウェア インベントリ
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b0e32fe31b69149bac4bac1796a0260763e9a078
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61164240"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a>ソフトウェア インベントリ - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

ソフトウェア インベントリは、脅威と脆弱性の管理共通プラットフォーム列挙[(CPE)](https://nvd.nist.gov/products/cpe)を使用して組織内の既知のソフトウェアの一覧です。 公式 CPE のないソフトウェア製品には、脆弱性が公開されません。 また、ベンダーの名前、弱点の数、脅威、公開されているデバイスの数などの詳細も含まれています。

## <a name="how-it-works"></a>しくみ

検出の分野では [、Microsoft Defender for Endpoint](overview-endpoint-detection-response.md)の検出および応答機能の検出と脆弱性評価を担当するシグナルの同じセットを活用しています。

リアルタイムで、数分で、脆弱性情報が発見されるのを見る事が可能です。 エンジンは、複数のセキュリティ フィードから情報を自動的に取得します。 実際には、特定のソフトウェアがライブ脅威キャンペーンに接続されている場合に表示されます。 また、利用可能な脅威分析レポートへのリンクもすぐに提供されます。

## <a name="navigate-to-the-software-inventory-page"></a>[ソフトウェア インベントリ] ページに移動します。

[ソフトウェア インベントリ] ページにアクセスするには、脅威と脆弱性の管理ポータルの [ソフトウェア インベントリ] [Microsoft 365 Defenderします](portal-overview.md)。

デバイスリストから個々のデバイス ページ内の特定のデバイス上のソフトウェア [を表示します](machines-view-overview.md)。

> [!NOTE]
> Microsoft Defender for Endpoint グローバル検索を使用してソフトウェアを検索する場合は、スペースの代わりにアンダースコアを付けなければなりません。 たとえば、最適な検索結果については、"Windows 10" または "Windows 11" ではなく "windows_10" または "windows_11" を記述します。

## <a name="software-inventory-overview"></a>ソフトウェア インベントリの概要

[ **ソフトウェア インベントリ]** ページが開き、ネットワークにインストールされているソフトウェアの一覧 (ベンダー名、見つかった弱点、関連する脅威、公開されたデバイス、露出スコアへの影響、タグなど) が表示されます。

リスト ビューは、ソフトウェアで見つかった弱点、関連付けられた脅威、およびソフトウェアがサポートの終了に達したかどうかのようなタグに基づいてフィルター処理できます。

:::image type="content" alt-text="ソフトウェア インベントリのランディング ページの例。" source="images/tvm-software-inventory.png" lightbox="images/tvm-software-inventory.png":::

調査するソフトウェアを選択します。 フライアウト パネルが開き、ページ上の情報がコンパクトに表示されます。 調査を深く掘り下げ、[ソフトウェアページを開く] を選択するか、[不正確なレポート] を選択して技術的な不整合にフラグ **を設定します**。

### <a name="software-that-isnt-supported"></a>サポートされていないソフトウェア

脅威によって現在サポートされていないソフトウェア& 脆弱性の管理[ソフトウェア インベントリ] ページに表示される場合があります。 サポートされていないので、限られたデータしか使用できません。 [弱さ] セクションの [使用できない] オプションを使用して、サポートされていないソフトウェアでフィルター処理します。

:::image type="content" alt-text="サポートされていないソフトウェア フィルター。" source="images/tvm-unsupported-software-filter.png" lightbox="images/tvm-unsupported-software-filter.png":::

以下は、ソフトウェアがサポートされていない状態を示しています。

- [弱点] フィールドには [使用できません] と表示されます。
- [公開されたデバイス] フィールドにダッシュが表示される
- サイド パネルとソフトウェア ページに追加された情報テキスト
- ソフトウェア ページには、セキュリティに関する推奨事項、検出された脆弱性、またはイベント タイムライン セクションが表示されません。

現在、CPE のない製品は、デバイス レベルのソフトウェア インベントリでのみ、ソフトウェア インベントリ ページに表示されません。

## <a name="software-inventory-on-devices"></a>デバイス上のソフトウェア インベントリ

ポータル ナビゲーション Microsoft 365 Defenderから、[デバイス インベントリ]**[に移動します](machines-view-overview.md)**。 デバイスページ (Computer1 など) を開くデバイスの名前を選択し、[ソフトウェア インベントリ] タブを選択して、デバイスに存在する既知のすべてのソフトウェアの一覧を表示します。 詳細については、特定のソフトウェア エントリを選択してフライアウトを開きます。

ソフトウェアは、現在デバイス でサポートされていない場合でも、デバイス レベルで表示脅威と脆弱性の管理。 ただし、使用できるデータは制限付きのみです。 ソフトウェアがサポートされていないかどうかは、[弱さ] 列に "使用できません" と表示されます。

CPE を持つソフトウェアは、このデバイス固有のソフトウェア インベントリの下に表示することもできます。

### <a name="software-evidence"></a>ソフトウェアの証拠

レジストリ、ディスク、または両方からデバイス上の特定のソフトウェアが検出された場所の証拠を参照してください。デバイス ソフトウェア インベントリ内の任意のデバイスで検索できます。

ソフトウェア名を選択して、フライアウトを開き、"Software Evidence" というセクションを探します。

:::image type="content" alt-text="デバイスの一覧からWindows 10証拠の例を示し、ソフトウェア証拠レジストリ パスを示します。" source="images/tvm-software-evidence.png" lightbox="images/tvm-software-evidence.png":::

## <a name="software-pages"></a>ソフトウェア ページ

ソフトウェア ページは、次に示すいくつかの方法で表示できます。

- ソフトウェア インベントリ ページ >ソフトウェア名を選択 **>で** [ソフトウェアを開く] ページを選択します。
- [[セキュリティに関する推奨事項>](tvm-security-recommendation.md) 選択] **>で** [ソフトウェアを開く] ページを選択します。
- [イベント タイムライン](threat-and-vuln-mgt-event-timeline.md)ページ > イベントを選択する > フライアウトの [関連コンポーネント] というセクションで、ハイパーリンクされたソフトウェア名 (Visual Studio 2017 など) を選択します。

 特定のソフトウェアのすべての詳細と次の情報が表示される完全なページ。

- ベンダー情報を含むサイド パネル、組織内のソフトウェアの普及率 (インストールされているデバイスの数、パッチが適用されていない公開されたデバイスを含む)、利用可能かどうかと悪用の可否、および露出スコアへの影響。
- 脆弱性と構成ミスの数と重大度を示すデータの視覚化。 また、公開されているデバイスの数を示すグラフも表示されます。
- 次のような情報を示すタブ。
  - 特定された弱点と脆弱性に対する対応するセキュリティ推奨事項。
  - 検出された脆弱性の名前付き CVEs。
  - ソフトウェアがインストールされているデバイス (デバイス名、ドメイン、OS などと共に)。
  - ソフトウェア のバージョン 一覧 (バージョンがインストールされているデバイスの数、検出された脆弱性の数、インストールされているデバイスの名前を含む)。

    :::image type="content" alt-text="ソフトウェアの詳細、Visual Studio、公開されているデバイスなど、2017 年のソフトウェアサンプル ページ。" source="images/tvm-software-page-example.png" lightbox="images/tvm-software-page-example.png":::

## <a name="report-inaccuracy"></a>レポートの不正確さ

あいまいな情報、不正確な情報、または不完全な情報が表示された場合は、誤検知を報告します。 既に修復済みのセキュリティ推奨事項について報告できます。

1. [ソフトウェア インベントリ] ページでソフトウェア フライアウトを開きます。
2. [ **不正確なレポート] を選択します**。
3. フライアウト ウィンドウで、ドロップダウン メニューから不正確なカテゴリを選択し、電子メール アドレスを入力し、不正確な情報の詳細を入力します。
4. **[送信]** を選択します。 フィードバックはすぐに専門家に脅威と脆弱性の管理されます。

## <a name="related-articles"></a>関連記事

- [脅威と脆弱性の管理概要](next-gen-threat-and-vuln-mgt.md)
- [セキュリティ上の推奨事項](tvm-security-recommendation.md)
- [イベントのタイムライン](threat-and-vuln-mgt-event-timeline.md)
- [Microsoft Defender for Endpoint Devices リストの表示と整理](machines-view-overview.md)
