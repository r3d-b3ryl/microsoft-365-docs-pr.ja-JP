---
title: Microsoft Defender for Business のレポート (プレビュー)
description: Microsoft Defender for Business で利用可能なレポートの概要を取得する (プレビュー)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 01/06/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 9d70984e4bce9cd7724326ca5f823fb9cf7d7440
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62464742"
---
# <a name="reports-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business のレポート (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐[](https://aka.ms/mdb-preview)々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは最初の一連 [のシナリオで](mdb-tutorials.md#try-these-preview-scenarios)起動し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 Microsoft Defender for Business (プレビュー) には、次の表に示すいくつかのレポートが含まれています。<br/><br/>

いくつかのレポートは、ポータル () Microsoft 365 Defender利用できます[https://security.microsoft.com](https://security.microsoft.com)。 この記事では、これらのレポート、それらを使用する方法、およびそれらを見つける方法について説明します。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

<br/><br/>

## <a name="reports-in-defender-for-business"></a>Defender for Business のレポート

|レポート  |説明  |
|---------|---------|
| **セキュリティ レポート**  | セキュリティ レポートには、組織の ID、デバイス、アプリに関する情報が表示されます。 このレポートにアクセスするには、ナビゲーション ウィンドウで [**ReportsGeneralSecurity** >  >  レポート **] を選択します**。 <br/><br/>**ヒント** 同様の情報は、ポータル () のホーム Microsoft 365 Defender表示できます [https://security.microsoft.com](https://security.microsoft.com)。 |
| **脅威保護**  | 脅威保護レポートは、アラートとアラートの傾向に関する情報を提供します。 [アラート **の傾向] 列** を使用して、過去 30 日間にトリガーされたアラートに関する情報を表示します。 [アラート **の状態]** 列を使用して、未解決のアラートのカテゴリや分類など、アラートに関する現在のスナップショット情報を表示します。 このレポートにアクセスするには、ナビゲーション ウィンドウで [**ReportsEndpointsThreat** >  >  **protection] を選択します**。 <br/><br/>**ヒント**: [インシデント] リストを使用 **して** 、アラートに関する情報を表示することもできます。 ナビゲーション ウィンドウで、[インシデント] **を選択して** 、現在のインシデントを表示および管理します。 詳細については、「Microsoft Defender for Business (プレビュー)でのインシデントの表示と [管理」を参照してください](mdb-view-manage-incidents.md)。 |
| **デバイスの正常性とコンプライアンス** | デバイスの正常性とコンプライアンス レポートには、デバイスの正常性と傾向に関する情報が表示されます。 このレポートを使用して、Defender for Business (プレビュー) センサーがデバイスで正しく動作し、デバイスの現在の状態をMicrosoft Defender ウイルス対策。 このレポートにアクセスするには、ナビゲーション ウィンドウで [**ReportsEndpointsDevice** >  >  **の正常性とコンプライアンス] を選択します**。 <br/><br/>**ヒント**: デバイス インベントリ リスト **を使用して** 、組織のデバイスに関する情報を表示できます。 ナビゲーション ウィンドウで、[デバイス インベントリ] **を選択します**。 詳細については、「Microsoft Defender for Business (プレビュー)でデバイスを管理 [する」を参照してください](mdb-manage-devices.md)。 |
| **脆弱なデバイス** | 脆弱なデバイス レポートは、デバイスと傾向に関する情報を提供します。 [傾向 **] 列** を使用して、過去 30 日間にアラートが発生したデバイスに関する情報を表示します。 [状態] **列を** 使用して、アラートがあるデバイスに関する現在のスナップショット情報を表示します。 このレポートにアクセスするには、ナビゲーション ウィンドウで [**ReportsEndpointsVulnerable** >  >  **デバイス] を選択します**。<br/><br/>**ヒント**: デバイス インベントリ リスト **を使用して** 、組織のデバイスに関する情報を表示できます。 ナビゲーション ウィンドウで、[デバイス インベントリ] **を選択します**。 詳細については、「Microsoft Defender for Business (プレビュー)でデバイスを管理 [する」を参照してください](mdb-manage-devices.md)。 |
| **Web 保護** | Web 保護レポートには、フィッシング サイト、マルウェア ベクター、悪用サイト、信頼されていないサイトまたは低評価サイト、明示的にブロックされているサイトにアクセスする試みが表示されます。 ブロックされたサイトのカテゴリには、アダルト コンテンツ、レジャー サイト、法的責任サイトなどがあります。 このレポートにアクセスするには、ナビゲーション ウィンドウで [**ReportsEndpointsWeb** >  protection] を > **選択します**。<br/><br/>**ヒント**: 組織の Web 保護をまだ構成していない場合は、レポート **ビュー** で [設定] ボタンを選択します。 次に、[ルール **] で** [ **Web コンテンツ フィルター] を選択します**。 Web コンテンツ フィルターの詳細については、「Web コンテンツ フィルター [」を参照してください](../defender-endpoint/web-content-filtering.md)。 |

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Business の使用を開始する (プレビュー)](mdb-get-started.md)

- [Microsoft Defender for Business でのインシデントの表示と管理 (プレビュー)](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business でデバイスを管理する (プレビュー)](mdb-manage-devices.md)
