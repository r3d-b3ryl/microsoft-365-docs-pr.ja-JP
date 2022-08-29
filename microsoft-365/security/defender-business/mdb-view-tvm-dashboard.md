---
title: Microsoft Defender for BusinessでMicrosoft Defender 脆弱性の管理ダッシュボードを表示する
description: Microsoft Defender 脆弱性の管理 ダッシュボードを使用して、Defender for Business で対処する重要な項目を確認します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/02/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.custom: intro-get-started
ms.openlocfilehash: dc1fea2a1bcbf05b0f32519221a68686a85e85f6
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326345"
---
# <a name="use-your-vulnerability-management-dashboard-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessで脆弱性管理ダッシュボードを使用する

Defender for Business には、セキュリティ チームの時間と労力を節約するように設計された脆弱性管理ダッシュボードが含まれています。 公開スコアを提供するだけでなく、そのダッシュボードを使用すると、公開されたデバイスに関する情報を表示し、関連するセキュリティに関する推奨事項を確認できます。 Defender 脆弱性管理ダッシュボードを使用すると、次のことができます。

- 会社のデバイスに関連付けられている露出スコアを表示します。
- デバイスとの通信障害への対処、ファイアウォール保護のオン、Microsoft Defender ウイルス対策定義の更新など、セキュリティに関する推奨事項を確認します。
- 検疫に送られたファイルや、デバイスに発見された脆弱性など、修復アクティビティを表示します。

## <a name="vulnerability-management-features-and-capabilities"></a>脆弱性管理機能と機能

Microsoft Defender for Businessの脆弱性管理機能と機能は次のとおりです。

- **ダッシュボード**: 脆弱性、公開、および推奨事項に関する情報を提供します。 最近の修復アクティビティ、公開されたデバイス、会社の全体的なセキュリティを向上させる方法を確認できます。 ダッシュボードの各カードには、より詳細な情報へのリンク、または推奨されるアクションを実行できるページへのリンクが含まれています。

    :::image type="content" source="media/mdb-mdvm-dashboard.png" alt-text="ダッシュボードMicrosoft Defender 脆弱性の管理スクリーンショット。" lightbox="media/mdb-mdvm-dashboard.png":::

- **推奨事項**: 現在のセキュリティに関する推奨事項と、確認および検討する関連する脅威情報を一覧表示します。 一覧で項目を選択すると、ポップアップ パネルが開き、実行できる脅威とアクションの詳細が表示されます。

- **修復**: 修復アクションとその状態を一覧表示します。 修復アクティビティには、ファイルの検疫への送信、プロセスの実行の停止、検出された脅威の実行のブロックなどがあります。 修復アクティビティには、デバイスの更新、ウイルス対策スキャンの実行などが含まれます。 

    :::image type="content" source="media/mdb-mdvm-remediation.png" alt-text="Microsoft Defender 脆弱性の管理修復のスクリーンショット。" lightbox="media/mdb-mdvm-remediation.png":::

- **インベントリ**: 組織内で現在使用されているソフトウェアとアプリを一覧表示します。 ブラウザー、オペレーティング システム、その他のソフトウェアがデバイスに表示され、弱点や脅威が特定されます。

- **弱点**: 脆弱性と、組織内で公開されているデバイスの数を一覧表示します。 [公開されているデバイス] 列に "0" と表示される場合は、すぐにアクションを実行する必要はありません。 ただし、このページに記載されている各脆弱性の詳細については、こちらを参照してください。 項目を選択して、その項目の詳細と、会社に対する潜在的な脅威を軽減するためにできることについて説明します。

    :::image type="content" source="media/mdb-mdvm-weakness-details.png" alt-text="Microsoft Defender 脆弱性の管理弱点のスクリーンショット。" lightbox="media/mdb-mdvm-weakness-details.png":::

- **イベント タイムライン**: タイムライン ビューで組織に影響を与える脆弱性を一覧表示します。   

[Microsoft Defender 脆弱性の管理の詳細については、こちらを参照してください](../defender-vulnerability-management/defender-vulnerability-management.md)。

## <a name="next-steps"></a>次の手順

- [Defender for Business でチュートリアルとシミュレーションを試す](mdb-tutorials.md)
- [Defender for Business へのデバイスのオンボード](mdb-onboard-devices.md)
- [Defender for Business でポリシーを表示または編集する](mdb-view-edit-create-policies.md)
