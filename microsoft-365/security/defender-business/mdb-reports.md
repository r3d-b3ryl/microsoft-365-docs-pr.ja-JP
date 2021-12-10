---
title: Microsoft Defender for Business のレポート
description: Microsoft Defender for Business で利用可能なレポートの概要を確認する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: f44eb6d339b1d8350486c5587c7a8a106280c807
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375796"
---
# <a name="reports-in-microsoft-defender-for-business"></a>Microsoft Defender for Business のレポート

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 この記事には、Microsoft Defender for Business (プレビュー) に含まれていない一部の機能について説明する可能性があるオンライン コンテンツへのリンクが含まれています。

Microsoft Defender for Business には、次の表に示すいくつかのレポートが含まれています。<br/><br/>


|レポート  |説明  |
|---------|---------|
| **セキュリティ レポート**  | セキュリティ レポートには、会社の ID、デバイス、アプリに関する情報が表示されます。 このレポートにアクセスするには、ナビゲーション ウィンドウで [レポート全般セキュリティ **レポート**  >  **]**  >  **を選択します**。 <br/><br/>**ヒント** 同様の情報は、ポータル () のホーム ページMicrosoft 365 Defender表示できます [https://security.microsoft.com](https://security.microsoft.com) 。 |
| **脅威保護**  | 脅威保護レポートは、アラートとアラートの傾向に関する情報を提供します。 [アラート **の傾向] 列** を使用して、過去 30 日間にトリガーされたアラートに関する情報を表示します。 [アラート **の状態]** 列を使用して、未解決のアラートのカテゴリや分類など、アラートに関する現在のスナップショット情報を表示します。 このレポートにアクセスするには、ナビゲーション ウィンドウで[レポート エンドポイント  >  **の脅威保護]**  >  **を選択します**。 <br/><br/>**ヒント**: [インシデント] リストを使用 **して** 、アラートに関する情報を表示することもできます。 ナビゲーション ウィンドウで、[インシデント] **を選択して** 、現在のインシデントを表示および管理します。 詳細については、「Microsoft Defender for Business でのインシデントの表示 [と管理」を参照してください](mdb-view-manage-incidents.md)。 |
| **デバイスの正常性とコンプライアンス** | デバイスの正常性とコンプライアンス レポートには、デバイスの正常性と傾向に関する情報が表示されます。 このレポートを使用して、Defender for Business センサーがデバイスで正しく動作するかどうか、およびデバイスの現在の状態をMicrosoft Defender ウイルス対策。 このレポートにアクセスするには、ナビゲーション ウィンドウで[レポート エンドポイント  >  **] [デバイス** の正常性  >  **とコンプライアンス] を選択します**。 <br/><br/>**ヒント**: デバイス インベントリ リスト **を使用して** 、会社のデバイスに関する情報を表示できます。 ナビゲーション ウィンドウで、[デバイス インベントリ] **を選択します**。 詳細については [、「Microsoft Defender for Business でデバイスを管理する」を参照してください](mdb-manage-devices.md)。 |
| **脆弱なデバイス** | 脆弱なデバイス レポートは、デバイスと傾向に関する情報を提供します。 [傾向 **] 列** を使用して、過去 30 日間にアラートが発生したデバイスに関する情報を表示します。 [状態] **列を** 使用して、アラートがあるデバイスに関する現在のスナップショット情報を表示します。 このレポートにアクセスするには、ナビゲーション ウィンドウで[レポート エンドポイントの脆弱な  >    >  **デバイス] を選択します**。<br/><br/>**ヒント**: デバイス インベントリ リスト **を使用して** 、会社のデバイスに関する情報を表示できます。 ナビゲーション ウィンドウで、[デバイス インベントリ] **を選択します**。 詳細については [、「Microsoft Defender for Business でデバイスを管理する」を参照してください](mdb-manage-devices.md)。 |
| **Web 保護** | Web 保護レポートには、フィッシング サイト、マルウェア ベクター、悪用サイト、信頼されていないサイトまたは低評価サイト、明示的にブロックされているサイトにアクセスする試みが表示されます。 ブロックされたサイトのカテゴリには、アダルト コンテンツ、レジャー サイト、法的責任サイトなどがあります。 このレポートにアクセスするには、ナビゲーション ウィンドウで[レポート エンドポイント Web 保護  >  **]**  >  **を選択します**。<br/><br/>**ヒント**: 会社の Web 保護をまだ構成していない場合は、レポートビューで [設定] ボタンを選択します。 次に、[ルール **] で**、[Web コンテンツ **フィルター] を選択します**。 Web コンテンツ フィルターの詳細については、「Web コンテンツ フィルター [」を参照してください](../defender-endpoint/web-content-filtering.md)。 |

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Business の使用を開始する](mdb-get-started.md)

- [Microsoft Defender for Business でのインシデントの表示と管理](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business でデバイスを管理する](mdb-manage-devices.md)
