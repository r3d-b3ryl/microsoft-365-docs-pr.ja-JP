---
title: Microsoft マネージド デスクトップを使用して Windows 11 をプレビューおよびテストする
description: 環境でWindows 11 を取得する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7c5526e532f14fc00ed52a6d260c017d0a019bae
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035464"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップを使用して Windows 11 をプレビューおよびテストする

 Microsoft Managed Desktop 環境内で Windows 11 互換テスト プログラムを登録して参加する方法。 通常、Windows 11 と Microsoft Managed Desktop の詳細については、「Windows [11」および「Microsoft Managed Desktop」を参照してください](../intro/win11-overview.md)。 

## <a name="add-devices-to-the-windows-11-test-group"></a>デバイスを 11 Windowsグループに追加する

要求に応じて、デバイス グループ **(Modern Workplace - Windows 11** プレリリース テスト デバイス) を作成し、11 のテストと評価Windowsします。 このグループのデバイスは、Windows 11 ビルドと Microsoft Managed Desktop ベースライン構成が使用可能になると、新しい構成を取得し、信頼性の問題を監視します。

Windows 11 テスト用に既存のデバイスまたは新しいデバイスを選択できますが、プレリリース ビルドでの欠陥や互換性の問題のリスクが高く、このグループに実稼働デバイスを登録する必要があります。 以前のデバイス グループの割り当ては、このグループへの割り当て時に削除されます。

プレリリース テスト グループにデバイスを登録するには、次の方法を実行します。

1. Microsoft Managed Desktop Service Engineering チームで新しいサービス要求を開きます。
2. フィールドには、次の値を使用します。
    - タイトル: Windows 11 互換登録
    - 要求の種類: 変更要求
    - カテゴリ: デバイス
    - サブカテゴリ: 展開グループの割り当て
3. [説明] フィールドに、11 テストで使用するデバイスのシリアルWindowsします。 指定したデバイスが Microsoft Managed Desktop テナントにまだ展開されていない場合は注意してください。

## <a name="prioritize-applications-to-submit-to-test-base"></a>テスト ベースに送信するアプリケーションの優先順位を設定する

ビジネスクリティカルなアプリケーションは、11 環境で閉じた環境での検証をWindows候補です。 使用状況と信頼性データに基づいて、Windows 11 テストのアプリの優先順位を設定できます。 推奨事項を要求するには、次の手順を実行します。

1. Microsoft Managed Desktop Service Engineering チームで新しいサービス要求を開きます。 要求をファイルする方法の詳細については、「管理者サポート」 [を参照してください](admin-support.md)。
2. フィールドには、次の値を使用します。
    - タイトル: Windows 11 名
    - 要求の種類: 情報の要求
    - カテゴリ: アプリ
    - サブカテゴリ: その他

## <a name="report-issues"></a>問題の報告

line-of-business または Windows アプリとの 11 の互換性の問題が発生した場合は、調査と修復Microsoft 365報告してください。 問題を報告するには、次の手順を実行します。

1. Microsoft Managed Desktop Service Engineering チームで新しいサービス要求を開きます。
2. フィールドには、次の値を使用します。
    - タイトル: Windows 11 の互換性テスト
    - 要求の種類: インシデント
    - カテゴリ: デバイス
    - サブカテゴリ: Windows/更新
3. 動作と、実稼働環境でのビジネスの妨げとなる深刻な状況を説明します。

Microsoft Managed Desktop は、生産性への影響に基づいてプレリリース ビルドの問題をトリアージして処理します。 サービスの説明ではプレリリース ビルドに関する問題は説明されませんが、ユーザーの生産性をブロックする問題が特定のテナント内で移行を開始する前に解決されるのを確認するために、お客様の管理者と連絡を取る予定です。
