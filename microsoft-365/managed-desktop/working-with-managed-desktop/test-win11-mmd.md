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
ms.openlocfilehash: 3e840a0af2313702686398fdef0e158bad0b74b8
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241169"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップを使用して Windows 11 をプレビューおよびテストする

この記事では、Microsoft Managed Desktop 環境内で Windows 11 互換テスト プログラムを登録して参加する方法について説明します。 Windows 11 および Microsoft Managed Desktop の詳細については、「Windows [11」および「Microsoft Managed Desktop」を参照してください](../intro/win11-overview.md)。  

## <a name="add-devices-to-the-windows-11-test-group"></a>デバイスを 11 Windowsグループに追加する

11 のテストと評価のために、デバイス グループ (モダン ワークプレース - Windows **11** プレリリース テスト デバイス) をWindowsしました。 名前の "プレリリース" にもかかわらず、このグループ内のデバイスは、Windows 11 の一般提供ビルドと、利用可能になると Microsoft Managed Desktop ベースライン構成を受け取る。 信頼性の問題が監視されています。

11 テストでは、新しいデバイスまたは既存のWindows使用できます。 ただし、テスト デバイスの互換性と全体的なエクスペリエンスに自信が持てない場合は、このグループに実稼働デバイスを登録する必要があります。

## <a name="prioritize-applications-to-submit-to-the-test-base"></a>アプリケーションに優先順位を付け、テスト ベースに送信する

ビジネスクリティカルなアプリケーションは、11 環境で閉じた環境での検証をWindows候補です。 使用状況と信頼性データに基づいて、Windows 11 テストのアプリを決定するのに役立ちます。 推奨事項を要求するには、次の手順を実行します。

1. Microsoft Managed Desktop Service Engineering チームで新しいサポート要求を開きます。 要求をファイルする方法の詳細については、「管理者サポート」 [を参照してください](admin-support.md)。
2. フィールドには、次の値を使用します。
    - タイトル: Windows 11 名
    - 要求の種類: 情報の要求
    - カテゴリ: アプリ
    - サブカテゴリ: その他

## <a name="report-issues"></a>問題の報告

line-of-business または Windowsアプリとの互換性に関する 11 の問題が見Microsoft 365、調査と修復のためにお問い合わせください。 問題を報告するには、次の手順を実行します。

1. Microsoft Managed Desktop Service Engineering チームで新しいサポート要求を開きます。
2. フィールドには、次の値を使用します。
    - タイトル: Windows 11 の互換性テスト
    - 要求の種類: インシデント
    - カテゴリ: デバイス
    - サブカテゴリ: Windows/更新

3. 動作と、実稼働環境でのビジネスの妨げとなる深刻な状況を説明します。

Microsoft Managed Desktop は、生産性への影響にWindows 11 の問題をトリアージして処理します。 要求を開いた後、顧客管理者と通信して、ユーザーの生産性をブロックする問題を確実に解決してから、特定のテナント内で Windows Windows 11 の移行を開始します。
