---
title: クラウド配信保護 Microsoft Defender ウイルス対策サンプルの提出
description: クラウド配信の保護とサンプル申請Microsoft Defender ウイルス対策について説明します
keywords: Microsoft Defender ウイルス対策、次世代テクノロジ、ウイルス対策サンプル申請、次世代 AV、機械学習、マルウェア対策、セキュリティ、防御、クラウド、クラウド配信の保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: jweston-1
ms.author: v-jweston
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 07/22/2021
ms.openlocfilehash: 6063aed4fcbd215e4acfcc1e265df5775c3105b7
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58561388"
---
# <a name="cloud-delivered-protection-antivirus-sample-submission"></a>クラウド配信の保護ウイルス対策サンプルの申請

Microsoft Defender for Endpoint Antivirus (Defender for Endpoint Antivirus) は、マルウェアの検出に多くのインテリジェントなメカニズムを使用します。 最も強力な機能の 1 つは、クラウドの機能を適用してマルウェアを検出する機能です。 Defender for Endpoint ウイルス対策クラウド保護は、エンドポイントの Defender for Endpoint ウイルス対策と組み合って、意思決定を行い、新しい脅威や新たな脅威からエンドポイントを保護します。

## <a name="microsoft-defender-for-endpoint-antivirus-cloud-protection-overview"></a>Microsoft Defender for Endpoint Antivirus クラウド保護の概要

クラウド保護は、Defender for Endpoint Antivirus で既定で有効になっています。 お客様は、Defender for Endpoint Antivirus でクラウド保護を無効にしない方が推奨されます。 クラウド保護を有効にすると、Defender for Endpoint ウイルス対策がクラウドに提供する情報 (サンプル申請を含む) を構成できます。 クラウド保護が有効になっているのは、他の特性に基づいて高信頼度の判断ができない場合に便利です。
サンプル申請を構成すると、その動作に関する質問が発生します。たとえば、データの格納方法と使用方法などです。 最も疑問を生む 3 つのクラウド保護サンプル提出オプションは次のとおりです。

- "安全なサンプルを自動的に送信する" (既定の動作)
- "すべてのサンプルを自動的に送信する"
- "サンプルを送信しない"

Intune、Configuration Manager、GPO、または PowerShell を使用した構成オプションの詳細については、「クラウドによる保護を有効にする」を参照[Microsoft Defender ウイルス対策。](enable-cloud-protection-microsoft-defender-antivirus.md)

## <a name="customer-data-cloud-protection-and-sample-submission"></a>顧客データ、クラウド保護、サンプル申請

Defender for Endpoint にオンボーディングを行う場合、Defender for Endpoint は、すべてのファイル サンプルを顧客データとして扱い、顧客が選択した地域とデータ保持の両方の選択肢を尊重します。 地域とデータ保持の選択肢については [、Microsoft Defender for Endpoint データストレージとプライバシーについて説明します](data-storage-privacy.md#data-storage-location)。
この製品は複数のコンプライアンス認定を受け、高度なコンプライアンス管理のセットへの継続的な遵守を実証しています。

- ISO 27001
- ISO 27018
- SOC I、II、III
- および PCI

[Azure Compliance Offerings は、](/azure/storage/common/storage-compliance-offerings) これらの認定に関する詳細を提供します。 Microsoft Defender for Endpoint のすべての認定成果物は、関連付けられた[](https://servicetrust.microsoft.com/)各 Azure 認定レポート内の Microsoft のサービス信頼ポータルにあります。

## <a name="cloud-protection-mechanisms"></a>クラウド保護メカニズム

Microsoft インテリジェント セキュリティ Graph、センサーの膨大なネットワークから脅威データを監視します。 クライアントからの信号とインテリジェント セキュリティ Graph のセンサーとデータの膨大なネットワークに基づいて評価を行えるクラウドベースの機械学習モデルを重ね合Graph。 このモデルは、Defender for Endpoint に対して、以前に見たことの多い脅威をブロックする機能を提供します。

Defender for Endpoint ウイルス対策およびクラウド保護は、次の方法を使用して、一目で見たことがない新しいほとんどの脅威を自動的にブロックします。

1. クライアント ベースの機械学習モデルを軽量にし、新しいマルウェアと未知のマルウェアをブロックします。

2. ローカルの動作分析、ファイル ベースの攻撃とファイルレス攻撃の停止。

3. 汎用的でヒューリスティックな手法を使用して一般的なマルウェアを検出する、高精度のウイルス対策。

4. エンドポイントで実行されている Defender for Endpoint ウイルス対策が、疑わしいファイルの意図を確認するためにより多くのインテリジェンスを必要とする場合に、高度なクラウドベースの保護が提供されます。

   1. Microsoft Defender for Endpoint ウイルス対策で明確な判断ができない場合、ファイル メタデータはクラウド保護サービスに送信されます。 通常、クラウド保護サービスは、ファイルが安全か悪意のあるかをミリ秒単位で判断できます。
      - ファイル メタデータのクラウド クエリは、動作、Web のマーク、または明確な判定が決定されないその他の特性の結果である可能性があります。
      - クリーンとマルウェアの評決に達する目的で、小さなメタデータ ペイロードが送信されます。
      - メタデータには、PE 属性、静的ファイル属性、動的属性、コンテキスト属性などがあります (図 1)。
      - 個人を特定できる情報 (PII) は含められない。 ファイル名などの情報はハッシュ化されます。
      - 同期または非同期を指定できます。 同期の場合、クラウドが評決をレンダリングするまでファイルは開かれません。 非同期の場合、クラウドが分析を実行している間にファイルが開きます。

   2. メタデータを調べた後、Defender for Endpoint ウイルス対策クラウド保護が決定的な評決に達できない場合は、ファイルのサンプルを要求して詳細な検査を行います。 この要求は、サンプル申請の設定構成を尊重します。

      1. **安全なサンプルを自動的に送信** する (既定)
         - セーフサンプルは、一般的に PII データが含まれていると見なされるサンプルです。.bat、.scr、.dll、.exe。
         - ファイルに PII が含まれている可能性がある場合、ユーザーはファイル サンプルの申請を許可する要求を取得します。
         - これは、macOS、Linux Windows既定です。

      2. **常にプロンプトを表示する**
         - 構成されている場合、ユーザーは常にファイル提出前に同意を求めるメッセージが表示されます
         - この設定は macOS クラウド保護では使用できません

      3. **すべてのサンプルを自動的に送信する**
         - 構成されている場合、すべてのサンプルが自動的に送信されます
         - Word ドキュメントに埋め込まれたマクロを含めるサンプル申請を行う場合は、[すべてのサンプルを自動的に送信する] を選択する必要があります。
         - この設定は、macOS クラウド保護では使用できません

      4. **送信しない**
         - ファイル サンプル分析に基づいて "一目でブロックする" の防止
         - "送信しない" は、macOS ポリシーの "Disabled" 設定と同じです。
         - サンプル提出が無効になっている場合でも、検出用にメタデータが送信されます。

   3. メタデータやファイルが Defender for Endpoint クラウドに送信された後、サンプル、起案、またはビッグデータ分析機械学習モデルを使用して、評決に達することができます。  このモデルを図 3 に示します。 クラウド配信の保護をオフにした場合、分析はローカルの機械学習モデルや同様の機能を通じてクライアントが提供できる機能にのみ制限されます。

_図 1 - Microsoft Defender クラウド保護に送信されるメタデータの例_:

:::image type="content" source="images/cloud-protection-metadata-sample.png" alt-text="図 1.Microsoft Defender Cloud Protection に送信されるメタデータの例。":::

_図 2.クラウド配信の保護フロー_:

:::image type="content" source="images/cloud-protection-flow.png" alt-text="図 2.クラウド配信の保護フロー。":::

_図 3.クラウドによる保護と層化された機械学習_:

:::image type="content" source="images/cloud-protection-detection-layered-machine-learning.png" lightbox="images/cloud-protection-detection-layered-machine-learning.png" alt-text="図 3.クラウドによる保護とレイヤー化された機械学習。":::

> [!NOTE]
>
> 「一目でブロックする (BAFS)」という語句も聞いたことがあります。 BAFS は、より正確な評決を提供する起訴など、クラウドが提供できるより広範な分析を指します。 これには、クラウド保護による尋問の下にあるファイルの開きを、評決に達するまで遅らせる場合もあります。 "サンプル申請" を無効にした場合、BAFS は無効になり、より広範な分析を行う必要があり、ファイル メタデータの分析にのみ限定されます。

## <a name="cloud-delivered-protection-levels"></a>クラウドによって提供される保護レベル

マルウェア検出では、可能な限り強力な保護を提供する一方で、誤検知の数を最小限に抑えることのバランスを取る必要があります。 異なる環境では、保護に対する許容範囲と誤検知のリスクがあります。 クラウド配信の保護レベルを使用すると、お客様は特定の環境に適した許容範囲レベルを定義できます。 クラウド配信保護を有効にした場合、正当なファイルを検出するリスクを高めることなく、強力な検出を提供するように保護レベルが自動的に構成されます。 別の保護レベルを構成する場合は、「クラウド配信の保護レベルを指定する」を参照[Microsoft Defender ウイルス対策。](specify-cloud-protection-level-microsoft-defender-antivirus.md)

> [!NOTE]
>
> 保護レベルを変更すると、誤検知のレベルが高くなる可能性があります。変更する前に注意深く評価する必要があります。
>

## <a name="other-file-sample-submission-scenarios"></a>その他のファイルサンプル提出シナリオ

Defender for Endpoint では、上記のクラウド保護設定に関連しないファイル サンプルを要求するシナリオが 2 つ追加されています。

### <a name="manual-file-sample-collection-by-security-admin-from-defender-for-endpoint-management-portal"></a>Defender for Endpoint Management Portal からのセキュリティ管理者による手動ファイル サンプル コレクション

デバイスを Microsoft Defender for Endpoint EDRオンボーディングする場合、デバイスからのサンプル コレクションを有効にする設定が設定されています。これは、上記の設定と混同される可能性があります。 この設定は、Defender for Endpoint 管理ポータルから要求された場合にデバイスからのファイル サンプル コレクションを制御します。これは、既に確立されている役割とアクセス許可の対象です。 この設定では、Defender for Endpoint ポータルのディープ分析などの機能について、エンドポイントからのファイルコレクションを許可またはブロックできます。 この設定が構成されていない場合、既定ではサンプル コレクションを有効にします。

Defender for Endpoint 構成設定の詳細については、「Defender for Endpoint でのデバイスのオンボード ツール[とメソッドWindows 10」を参照してください。](configure-endpoints.md)

### <a name="automated-investigation-and-response-content-analysis"></a>自動調査と応答のコンテンツ分析

自動調査がデバイスで実行されている場合 (アラートに応答して自動的に実行するか、手動で実行するように構成されている場合)、疑わしいと識別されたファイルをエンドポイントから収集して、詳細な検査を行うことができます。 Defender for Endpoint ポータルでは、自動調査のファイル コンテンツ分析機能を無効にできます。 ファイル拡張子の名前を変更して、自動調査中に自動的に提出される他のファイルの種類の拡張子を追加または削除することもできます。

[自動化ファイルのアップロードを管理する](manage-automation-file-uploads.md)
