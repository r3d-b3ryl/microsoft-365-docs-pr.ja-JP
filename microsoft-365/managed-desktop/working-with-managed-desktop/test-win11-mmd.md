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
ms.openlocfilehash: 82da735dcf5e9c83fc70d34c0380dc290e4f81f7
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172345"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップを使用して Windows 11 をプレビューおよびテストする

Microsoft Managed Desktop 環境内で Windows 11 互換テスト プログラムを登録して参加する方法。 通常、Windows 11 と Microsoft Managed Desktop の詳細については、「Windows [11」および「Microsoft Managed Desktop」を参照してください](../intro/win11-overview.md)。 

## <a name="add-devices-to-the-windows-11-test-group"></a>デバイスを 11 Windowsグループに追加する

デバイス グループ (Modern Workplace - Windows **11** プレリリース テスト デバイス) を作成し、11 のテストと評価Windowsしました。 名前の 「プレリリース」 にもかかわらず、このグループ内のデバイスは、Windows 11 の一般提供ビルドと Microsoft Managed Desktop ベースライン構成が使用可能になると受信し、信頼性の問題を監視します。 

Windows 11 テスト用に既存のデバイスまたは新しいデバイスを選択できますが、テスト デバイスの互換性と全体的なエクスペリエンスに自信が持てない場合は、このグループに実稼働デバイスを登録する必要があります。 

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

Microsoft Managed Desktop は、生産性への影響にWindows 11 の問題をトリアージして処理します。 要求を開いた際に、ユーザーの生産性をブロックする問題が解決された後、特定のテナント内でより広範な Windows Windows 11 移行を開始する前に、お客様の管理者に依頼します。
