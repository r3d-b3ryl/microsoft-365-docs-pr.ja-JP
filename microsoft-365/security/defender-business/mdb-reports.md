---
title: Microsoft Defender for Businessのレポート
description: Defender for Business のセキュリティ レポートの概要を確認します。 レポートには、検出された脅威、アラート、脆弱性、デバイスの状態が表示されます。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: a4fbfc830c349df69180524305339582f444a609
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2022
ms.locfileid: "65174832"
---
# <a name="reports-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessのレポート

Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) では、いくつかのレポートを使用できます。 この記事では、これらのレポート、それらを使用する方法、およびそれらを見つける方法について説明します。

## <a name="reports-in-defender-for-business"></a>Defender for Business のレポート

|レポート  |説明  |
|---------|---------|
| **セキュリティ レポート**  | セキュリティ レポートには、会社の ID、デバイス、アプリに関する情報が表示されます。 このレポートにアクセスするには、ナビゲーション ウィンドウで **ReportsGeneralSecurity** >  >  **レポート** を選択します。 <br/><br/>**ヒント** 同様の情報は、Microsoft 365 Defender ポータル ()[https://security.microsoft.com](https://security.microsoft.com) のホーム ページで確認できます。 |
| **脅威保護**  | 脅威保護レポートは、アラートとアラートの傾向に関する情報を提供します。 [ **アラートの傾向** ] 列を使用して、過去 30 日間にトリガーされたアラートに関する情報を表示します。 **[アラートの状態**] 列を使用して、未解決のアラートのカテゴリや分類など、アラートに関する現在のスナップショット情報を表示します。 このレポートにアクセスするには、ナビゲーション ウィンドウで **ReportsEndpointsThreat** >  >  **保護** を選択します。 <br/><br/>**ヒント**: [ **インシデント]** リストを使用して、アラートに関する情報を表示することもできます。 ナビゲーション ウィンドウで [インシデント] を選択し、現在 **の** インシデントを表示および管理します。 詳細については、「[Microsoft Defender for Businessでのインシデントの表示と管理](mdb-view-manage-incidents.md)」を参照してください。 |
| **デバイスの正常性とコンプライアンス** | デバイスの正常性とコンプライアンス レポートは、デバイスの正常性と傾向に関する情報を提供します。 このレポートを使用して、Defender for Business センサーがデバイスで正しく動作しているかどうかと、Microsoft Defender ウイルス対策の現在の状態を判断できます。 このレポートにアクセスするには、ナビゲーション ウィンドウで **ReportsEndpointsDevice** >  >  の **正常性とコンプライアンスを** 選択します。 <br/><br/>**ヒント**: **デバイス インベントリ** リストを使用して、会社のデバイスに関する情報を表示できます。 ナビゲーション ウィンドウで、[ **デバイス インベントリ**] を選択します。 詳細については、「[Microsoft Defender for Businessでデバイスを管理](mdb-manage-devices.md)する」を参照してください。 |
| **脆弱なデバイス** | 脆弱なデバイス レポートには、デバイスと傾向に関する情報が表示されます。 [ **傾向** ] 列を使用して、過去 30 日間にアラートが表示されたデバイスに関する情報を表示します。 **[状態]** 列を使用して、アラートがあるデバイスに関する現在のスナップショット情報を表示します。 このレポートにアクセスするには、ナビゲーション ウィンドウで **ReportsEndpointsVulnerable** >  >  **デバイスを** 選択します。<br/><br/>**ヒント**: **デバイス インベントリ** リストを使用して、会社のデバイスに関する情報を表示できます。 ナビゲーション ウィンドウで、[ **デバイス インベントリ**] を選択します。 詳細については、「[Microsoft Defender for Businessでデバイスを管理](mdb-manage-devices.md)する」を参照してください。 |
| **Web 保護** | Web 保護レポートには、フィッシング サイト、マルウェア ベクトル、悪用サイト、信頼されていないサイトまたは低評価のサイト、および明示的にブロックされているサイトへのアクセス試行が表示されます。 ブロックされたサイトのカテゴリには、成人コンテンツ、娯楽サイト、法的責任サイトなどがあります。 このレポートにアクセスするには、ナビゲーション ウィンドウで **ReportsEndpointsWeb** >  >  **保護** を選択します。<br/><br/>**ヒント**: 会社の Web 保護をまだ構成していない場合は、レポート ビューで **[設定**] ボタンを選択します。 次に、[ **ルール]** で [ **Web コンテンツ フィルター**] を選択します。 Web コンテンツ のフィルター処理の詳細については、「 [Web コンテンツ のフィルター処理](../defender-endpoint/web-content-filtering.md)」を参照してください。 |

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Businessを使用した概要](mdb-get-started.md)
- [Microsoft Defender for Businessでのインシデントの表示と管理](mdb-view-manage-incidents.md)
- [Microsoft Defender for Businessでデバイスを管理する](mdb-manage-devices.md)
