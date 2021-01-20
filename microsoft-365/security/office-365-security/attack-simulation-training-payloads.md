---
title: 攻撃シミュレーション トレーニング用のペイロードを作成する
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Office 365 向け Microsoft Defender で攻撃シミュレーション トレーニング用のカスタム ペイロードを作成する方法について説明します。
ms.openlocfilehash: 86a962dc3117708ac71195b9efc336fa30c573dd
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908343"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>攻撃シミュレーショントレーニングのカスタム ペイロードを作成する

Microsoft は、さまざまなソーシャル エンジニアリング手法に対応した堅牢なペイロード カタログを提供し、攻撃シミュレーション トレーニングと組み合わせ可能です。 ただし、組織に対してより良く機能するカスタム ペイロードを作成する必要がある場合があります。 この記事では、Microsoft Defender で 365 用の攻撃シミュレーション トレーニングでペイロードOffice説明します。

ペイロードを作成するには、専用の [Payloads] タブまたはシミュレーション作成ウィザードで [Create **a** [ **payload]**](https://security.microsoft.com/attacksimulator?viewid=payload) (ペイロードの作成) [をクリックします](attack-simulation-training.md#selecting-a-payload)。

ウィザードの最初の手順では、ペイロードの種類を選択します。 **現時点では、電子メールのみを利用できます**。

次に、関連付けられている手法を選択します。 技術の詳細については、「ソーシャル エンジニアリング手法の選択 [」を参照してください](attack-simulation-training.md#selecting-a-social-engineering-technique)。

次の手順では、ペイロードに名前を付けています。 必要に応じて、説明を指定できます。

## <a name="configure-payload"></a>ペイロードを構成する

次に、ペイロードをビルドします。 [送信者の詳細] セクションに、送信者の名前、メール アドレス、メールの **件名を入力** します。 指定された一覧からフィッシング URL を選ぶ。 この URL は、後でメッセージの本文に埋め込まれる予定です。

> [!TIP]
> ペイロードの送信者の内部電子メールを選択すると、ペイロードは会社の別の従業員から送信されたメールとして表示されます。 これによりペイロードの影響を受けやすくなり、内部の脅威のリスクについて従業員を教育するのに役立ちます。

ペイロードを作成するには、リッチ テキスト エディターを使用できます。 事前に作成したメールをインポートできます。 メールの本文を作成する場合は、動的タグを利用して、ターゲットに合った電子メールをカスタマイズします。 [ **フィッシング] リンクを** クリックして、以前に選択したフィッシング URL をメッセージの本文に追加します。

![Microsoft Defender for Office 365 のペイロード作成で強調表示されたフィッシング リンクと動的タグ](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> 時間を節約するには、電子メール メッセージ内のすべてのリンクをフィッシング リンクに置き換える **オプションをオンに切り替える必要があります**。

必要に合ったペイロードの作成が完了したら、[次へ] をクリック **します**。

## <a name="adding-indicators"></a>インジケーターの追加

インジケーターは、攻撃シミュレーションを通過する従業員が、将来の攻撃で探す手がかりを理解するのに役立ちます。 開始するには、[インジケーターの追加 **] をクリックします**。

ドロップダウン リストから使用するインジケーターを選択します。 この一覧は、フィッシングメール メッセージに表示される最も一般的な手がかりを含む目的で作成されています。 選択したら、インジケーターの配置が電子メールの本文からに設定され、[テキストの選択] を **クリックします**。 このインジケーターが表示されるペイロードの部分を強調表示し、[選択] をクリック **します**。

![攻撃シミュレーション トレーニングのインジケーターに追加するメッセージ本文の強調表示されたテキスト](../../media/attack-sim-preview-select-text.png)

インジケーターを説明するカスタム説明を追加し、インジケータープレビュー フレーム内をクリックしてインジケーターのプレビューを表示します。 完了したら、[追加] を **クリックします**。 ペイロード内のすべてのインジケーターをカバーするまで、これらの手順を繰り返します。

## <a name="review-payload"></a>ペイロードを確認する

ペイロードの作成は完了です。 次に、詳細を確認し、ペイロードのプレビューを表示します。 プレビューには、作成したインジケーターすべてが含まれます。 この手順では、ペイロードの各部分を編集できます。 問題がなければ、ペイロード **を送信** できます。

> [!IMPORTANT]
> 作成したペイロードには、 **テナントがソース** として含まれます。 ペイロードを選択する場合は、テナントをフィルターで削除しなけれと **します**。

## <a name="related-links"></a>関連リンク

[攻撃シミュレーション トレーニングの使用を開始する](attack-simulation-training-get-started.md)

[フィッシング攻撃シミュレーションを作成する](attack-simulation-training.md)

[攻撃シミュレーション トレーニングを通して洞察を得る](attack-simulation-training-insights.md)
