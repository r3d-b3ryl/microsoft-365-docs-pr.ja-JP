---
title: Microsoft 365 正常性ダッシュボード
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
description: Microsoft 365 Health ダッシュボードの概要と、Microsoft 365 組織の正常性に関する最新の状態を維持するための役割について説明します。
ms.openlocfilehash: 8ee088f2611cf57576897dc4553ac3f21076f922
ms.sourcegitcommit: aa9e1bceb661df894f66d5dd5f4ab692c870fc71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2022
ms.locfileid: "66994580"
---
# <a name="microsoft-365-health-dashboard"></a>Microsoft 365 Health ダッシュボード

組織の管理者は、限られた時間で多くのアプリやサービスをスムーズに実行し続けることに課金されます。 Microsoft 365 Health ダッシュボードは、組織内でアプリやサービスがどれだけ正常に実行されているかを理解するのに役立つダッシュボードを作成しました。

正常性ダッシュボードは、環境の全体的な正常性のスナップショットを提供するように設計されています。 組織がデスクトップ ソフトウェアを最新の状態に保ち、セキュリティに関するベスト プラクティスに従い、支払った製品とサービスを使用していることを確認できます。

> [!NOTE]
> Microsoft 365 Health ダッシュボードはパブリック プレビュー段階にあり、一部のお客様が利用できるわけではありません。

## <a name="health-dashboard-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの正常性ダッシュボード

1. 管理センターにサインインし、次の URL に移動します https://admin.microsoft.com/AdminPortal/Home?#/healthoverview。

正常性ダッシュボードにアクセスするには、グローバル管理者ロールまたはグローバル リーダー ロールのメンバーである必要があります。

:::image type="content" source="../../media/health-dashboard-view.png" alt-text="正常性ダッシュボード":::

ダッシュボードの上部には、注意が必要な問題に関する重要なアラートが表示されます。  次の 2 種類の通知が表示されます。

- 一般的なサービス インシデント。

- 有効期限が切れたサブスクリプションなど、今後の問題を引き起こす可能性がある課金の問題。

アラートがない場合は、緑色のバナーを使用すると、正常性ダッシュボードで問題が見つからなかったことを確認できます。

### <a name="service-health-and-usage"></a>サービス正常性と使用方法

ページの中央に、上位のアプリとサービスの現在のサービス正常性状態が表示されます。 これは、上位の製品の選択されたビューです。 すべての製品の一覧を表示する場合は、リンクに従って完全な一覧を表示できます。 このセクションでは、1 日の平均使用量とライセンス使用率のビューも示します。 これにより、組織内で製品がどのように使用されているかを理解するのに役立ちます。

:::image type="content" source="../../media/service-health-usage.png" alt-text="スクリーンショット: 正常性ダッシュボード サービスの正常性と使用状況":::

### <a name="microsoft-365-app-updates"></a>Microsoft 365 アプリの更新プログラム

ソフトウェア更新プログラムを最新の状態に保つために、ダッシュボードのこのセクションでは、Word、Excel、PowerPoint などの Microsoft 365 デスクトップ アプリが最新の状態であるかどうかを一目で確認できます。 一部のデバイスが遅れている場合は、リスクを理解するのに役立つデバイスと脆弱性の一覧が表示されます。 この情報は、[ソフトウェア 更新] ページを使用して提供されます。詳細については、このページにアクセスできます。

:::image type="content" source="../../media/app-updates.png" alt-text="スクリーンショット: 正常性ダッシュボード アプリの更新情報":::

### <a name="recommended-actions"></a>推奨処理

ダッシュボードの下部には、組織の正常性を向上させるためにできることに関する推奨事項が表示されます。

- **多要素認証を有効にする: 多要素認証** (MFA) に対して現在有効になっているアカウントの数の概要と、MFA セットアップ ウィザードへのリンクを参照してください。

- **Office の毎月の更新プログラムを有効にする**: 6 か月に 1 回以上更新プログラムを受け取ることができるように、組織の Office 更新プログラムの頻度が設定されているかどうかを確認します。

- **OneDrive トレーニングを共有** する: ランサムウェアやデバイスの障害に対する復旧に役立つファイルを OneDrive に保存するようユーザーに勧めます。 OneDrive のセットアップと使用に役立つビデオの概要を送信します。

## <a name="note-for-microsoft-enterprise-customers"></a>Microsoft エンタープライズのお客様向けの注

正常性ダッシュボードの初期バージョンは、小規模な IT チームに焦点を当てています。このチームは、1 人のユーザーが Microsoft 365 を管理するのが一般的です。 ダッシュボードを進化させて、時間の経過と共に、より多くの IT ロールと大規模な組織のニーズに対応する予定です。
