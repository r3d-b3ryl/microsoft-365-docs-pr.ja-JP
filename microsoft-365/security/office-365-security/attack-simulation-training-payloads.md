---
title: 攻撃シミュレーション トレーニングのペイロードを作成する
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Microsoft Defender で攻撃シミュレーション トレーニング用のカスタム ペイロードを作成する方法をOffice 365。
ms.technology: mdo
ms.openlocfilehash: ac7963b71c466e8dfdc513a2563776cd4e10af95
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878762"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>攻撃シミュレーショントレーニングのカスタム ペイロードを作成する

**Microsoft** Defender for [Office 365プラン 2 に適用されます](defender-for-office-365.md)

Microsoft は、攻撃シミュレーション トレーニングと組み合わせ、さまざまなソーシャル エンジニアリング手法の堅牢なペイロード カタログを提供しています。 ただし、組織に合ったカスタム ペイロードを作成することもできます。 この記事では、Microsoft Defender の攻撃シミュレーション トレーニングでペイロードを作成する方法についてOffice 365。

ペイロードを作成するには、[専用のペイロード]タブまたはシミュレーション作成ウィザードで [ペイロードの作成[] をクリックします](attack-simulation-training.md#selecting-a-payload)。 [  ](https://security.microsoft.com/attacksimulator?viewid=payload)

ウィザードの最初の手順では、ペイロードの種類を選択します。 **現在、電子メールのみを使用できます**。

次に、関連付けられた手法を選択します。 技術の詳細については [、「Selecting a social engineering technique 」を参照してください](attack-simulation-training.md#selecting-a-social-engineering-technique)。

次の手順では、ペイロードに名前を付けています。 必要に応じて、説明を指定できます。

## <a name="configure-payload"></a>ペイロードの構成

次に、ペイロードをビルドします。 [送信者の詳細] セクションに、送信者の名前、電子メール アドレス、および電子メールの件名 **を入力** します。 指定されたリストからフィッシング URL を選択します。 この URL は、後でメッセージの本文に埋め込まれる予定です。

> [!TIP]
> ペイロードの送信者に対して内部メールを選択すると、そのペイロードが会社の別の従業員からのメールとして表示されます。 これにより、ペイロードの影響を受けやすくし、内部の脅威のリスクについて従業員を教育するのに役立ちます。

リッチ テキスト エディターを使用してペイロードを作成できます。 事前に作成したメールをインポートできます。 電子メールの本文を作成する場合は、動的タグを利用して、メールをターゲットに合ってカスタマイズします。 [ **フィッシング] リンクをクリック** して、以前に選択したフィッシング URL をメッセージの本文に追加します。

![Microsoft Defender のペイロードの作成で強調表示されているフィッシング リンクと動的Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> 時間を節約するには、電子メール メッセージ内のすべてのリンクをフィッシング リンクに置き換える **オプションをオンにします**。

ペイロードの作成が完了したら、[次へ] を **クリックします**。

## <a name="adding-indicators"></a>インジケーターの追加

インジケーターは、攻撃シミュレーションを実行する従業員が、将来の攻撃で探す手がかりを理解するのに役立ちます。 開始するには、[インジケーターの追加 **] をクリックします**。

ドロップダウン リストから使用するインジケーターを選択します。 このリストは、フィッシングメール メッセージに表示される最も一般的な手がかりを含むキュアリングされます。 選択したら、インジケーターの配置が [メールの本文から] に設定され、[テキストの選択] を **クリックします**。 このインジケーターが表示されるペイロードの部分を強調表示し、[選択] を **クリックします**。

![攻撃シミュレーション トレーニングでインジケーターに追加するメッセージ本文の強調表示されたテキスト](../../media/attack-sim-preview-select-text.png)

インジケーターを説明するカスタムの説明を追加し、インジケーターのプレビュー フレーム内をクリックすると、インジケーターのプレビューが表示されます。 完了したら、[追加] を **クリックします**。 ペイロード内のすべてのインジケーターをカバーするまで、これらの手順を繰り返します。

## <a name="review-payload"></a>ペイロードの確認

ペイロードの構築は完了です。 次に、詳細を確認し、ペイロードのプレビューを確認します。 プレビューには、作成したインジケーターすべてが含まれます。 この手順では、ペイロードの各部分を編集できます。 完了したら、ペイロード **を送信** できます。

> [!IMPORTANT]
> 作成したペイロードには、テナント **がソース** として含まれます。 ペイロードを選択する場合は、テナントをフィルター処理しない必要 **があります**。

## <a name="related-links"></a>関連リンク

[攻撃シミュレーション トレーニングの使用を開始する](attack-simulation-training-get-started.md)

[フィッシング攻撃シミュレーションの作成](attack-simulation-training.md)

[攻撃シミュレーション トレーニングを通して洞察を得る](attack-simulation-training-insights.md)
