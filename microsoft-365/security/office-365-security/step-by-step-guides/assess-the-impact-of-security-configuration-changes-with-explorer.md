---
title: エクスプローラーを使用して、セキュリティ構成の変更の影響を評価する
description: エクスプローラーを使用して、Microsoft Defender for Office 365におけるセキュリティ制御 (構成) の変更の影響を判断する例とチュートリアル
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTBen
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: b710fe78c141cd1f2c0b4461ded6e3f485276616
ms.sourcegitcommit: a209c9f86a7b4340a426c4cfed2d36a388c71124
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66798226"
---
# <a name="assess-the-impact-of-security-configuration-changes-with-explorer"></a>エクスプローラーを使用して、セキュリティ構成の変更の影響を評価する

ポリシーやトランスポート ルールなどのセキュリティ構成に変更を加える前に、組織の中断を *最小限に抑* えて計画できるように、変更の影響を理解しておくことが重要です。

このステップ バイ ステップ ガイドでは、変更を評価し、影響を受けたメールをエクスポートして評価します。 このプロシージャは、エクスプローラーで使用する条件 (フィルター) を変更することで、さまざまな変更に適用できます。

## <a name="what-youll-need"></a>必要なもの

- Microsoft Defender for Office 365プラン 2 (E5 の一部として含まれています)。
- 十分なアクセス許可 (脅威エクスプローラーを使用して評価するために最低限必要なセキュリティ リーダー)。
- 次の手順を実行するには、5 分から 10 分かかります。

## <a name="assess-changing-normal-confidence-phish-delivery-location-to-quarantine-from-the-junk-email-folder"></a>通常の信頼度フィッシング配信場所を検疫に変更する (迷惑メール フォルダーから) 評価する

1. セキュリティ ポータルに **ログイン** し、エクスプローラー (左側のナビゲーションにある *Email & コラボレーション* の下) <https://security.microsoft.com/threatexplorer>に移動します。
1. 上部のタブの選択から **[フィッシング** ] を選択します (*すべてのメール* が既定のビューです)。
1. **フィルター** ボタン (既定は *Sender*) を押し、**フィッシングの信頼レベル** を選択します。
1. **[標準] の [フィッシング信頼レベル**] を選択 **します**。
1. **元の配信場所** セットの **フィルター** を **迷惑フォルダー** として追加します。
1. **[更新] を押します**。 エクスプローラーがフィルター処理され、 *信頼度の高いフィッシング* として検出され、スパム対策ポリシーの設定が原因で迷惑メール フォルダーに配信されるすべてのメールが表示されるようになりました。
1. グラフに表示されるデータをピボットする場合は、グラフ **の左上のデータ スライサー (既定では *配信アクション*)** を使用し、 **送信者 IP** や **送信者ドメイン** などの有用なデータを選択して、傾向や影響を受ける上位の送信者を特定できます。
1. グラフ セクションの下で、影響を受けるメールが表示されたら、[ **電子メール リストのエクスポート**] を選択します。これにより、オフライン分析用の CSV が生成されます。 **これは、フィッシングアクションが検疫に変更された場合に検疫される電子メールの一覧です (標準プリセットと厳密なプリセットの両方に推奨される変更)。**

## <a name="assess-removing-a-sender--domain-override-removal"></a>送信者/ドメインオーバーライドの削除の削除を評価する

1. セキュリティ ポータルに **ログイン** し、**エクスプローラー** (左側のナビゲーションにある Email & コラボレーションの下) <https://security.microsoft.com/threatexplorer>に移動します。
1. まだ選択されていない場合 **は、[すべてのメール** ] を選択します。
1. **フィルター** ボタン (既定では *Sender*) を押し、送信者または送信者のドメイン フィルターを追加してから、削除の影響を評価するエントリを追加します。
1. 日付範囲を最大&に展開 **します。[更新] を** 押すと、送信者/送信ドメインが組織のメッセージングでまだアクティブな場合は、メールが一覧表示されます。 フィルターを調整する必要 *がある場合や* 、そのドメイン/送信者からメールを受信しなくなった場合は、エントリを安全に削除できます。
1. メールが一覧表示されている場合は、エントリがまだアクティブな送信者であることを意味します。 データ スライサー (既定では *配信アクション*) を使用して、グラフ内のデータを **検出テクノロジ** にピボットします。
1. グラフを更新する必要があり、データが表示されない場合は、前に示したメールに対する脅威が検出されていないことを意味します。これは、オーバーライドする検出がないため、オーバーライドは必要ないことを示します。
1. **検出テクノロジ** によってデータがスライスされたときにデータが表示される場合、これは、保護スタックがアクションを実行しているため、オーバーライドを削除すると、この送信者/ドメインに影響を与 *える可能性* があることを意味します。
1. メールが本当に悪意があり、エントリを削除できるか、または *誤検知* であり、脅威として誤って検出されないように修復する必要があるかどうかを評価するには、さらに調査する必要があります (認証は誤検知の最大の原因です)。

### <a name="further-reading"></a>その他の読み取り

セキュリティ で保護されたプリセットを使用することを検討してください。事前[設定されたセキュリティ ポリシーを使用して常に最適なセキュリティ制御](/microsoft-365/security/office-365-security/step-by-step-guides/ensuring-you-always-have-the-optimal-security-controls-with-preset-security-policies)を確保する

スプーフィン[グ インテリジェンス スプーフィング インテリジェンス分析情報](/microsoft-365/security/office-365-security/learn-about-spoof-intelligence)を使用して、電子メール認証の問題を管理することもできます

Exchange Online Protectionでの電子メール認証[Email認証の](/microsoft-365/security/office-365-security/email-validation-and-authentication)詳細を確認する
