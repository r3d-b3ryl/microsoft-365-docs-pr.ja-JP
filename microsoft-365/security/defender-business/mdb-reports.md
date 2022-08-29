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
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: fe74557403791c759838dbf6d632bc50b59698cf
ms.sourcegitcommit: 9b10e56b9e83f3a80757fa6108bebd1d80cf4178
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67320374"
---
# <a name="reports-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessのレポート

複数のレポートが、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で利用できます。 この記事では、これらのレポート、それらを使用する方法、およびそれらを見つける方法について説明します。

## <a name="reports-in-defender-for-business"></a>Defender for Business のレポート

|レポート  |説明  |
|---------|---------|
| **セキュリティ レポート**  | セキュリティ レポートには、会社の ID、デバイス、アプリに関する情報が表示されます。 このレポートにアクセスするには、ナビゲーション ウィンドウで [ **レポート** > **全般** > **セキュリティ レポート**] を選択します。 <br/><br/>同様の情報は、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) のホーム ページで確認できます。 |
| **脅威保護**  | 脅威保護レポートは、アラートとアラートの傾向に関する情報を提供します。 [ **アラートの傾向** ] 列を使用して、過去 30 日間にトリガーされたアラートに関する情報を表示します。 **[アラートの状態**] 列を使用して、未解決のアラートのカテゴリや分類など、アラートに関する現在のスナップショット情報を表示します。 このレポートにアクセスするには、ナビゲーション ウィンドウで [ **Reports** > **Endpoints** > **Threat Protection**] を選択します。 <br/><br/>[ **インシデント] リストを** 使用して、アラートに関する情報を表示することもできます。 ナビゲーション ウィンドウで [インシデント] を選択し、現在 **の** インシデントを表示および管理します。 詳細については、「 [Defender for Business でのインシデントの表示と管理」を](mdb-view-manage-incidents.md)参照してください。 |
| **デバイスの正常性とコンプライアンス** | デバイスの正常性とコンプライアンス レポートは、デバイスの正常性と傾向に関する情報を提供します。 このレポートを使用して、Defender for Business センサーがデバイスで正しく動作しているかどうか、および Microsoft Defender ウイルス対策の現在の状態を判断できます。 このレポートにアクセスするには、ナビゲーション ウィンドウで [ **レポート** > **エンドポイント デバイスの** > **正常性とコンプライアンス**] を選択します。 <br/><br/>**デバイス インベントリ** リストを使用して、会社のデバイスに関する情報を表示できます。 ナビゲーション ウィンドウで、[ **デバイス インベントリ**] を選択します。 詳細については、「 [Defender for Business でデバイスを管理する」を](mdb-manage-devices.md)参照してください。 |
| **脆弱なデバイス** | 脆弱なデバイス レポートには、デバイスと傾向に関する情報が表示されます。 [ **傾向** ] 列を使用して、過去 30 日間にアラートが表示されたデバイスに関する情報を表示します。 **[状態]** 列を使用して、アラートがあるデバイスに関する現在のスナップショット情報を表示します。 このレポートにアクセスするには、ナビゲーション ウィンドウで [ **レポート** > **エンドポイントの** > **脆弱なデバイス**] を選択します。<br/><br/>**ヒント**: **デバイス インベントリ** リストを使用して、会社のデバイスに関する情報を表示できます。 ナビゲーション ウィンドウで、[ **デバイス インベントリ**] を選択します。 詳細については、「 [Defender for Business でデバイスを管理する」を](mdb-manage-devices.md)参照してください。 |
| **Web 保護** | Web 保護レポートには、フィッシング サイト、マルウェア ベクトル、悪用サイト、信頼されていないサイトまたは低評価のサイト、および明示的にブロックされているサイトへのアクセス試行が表示されます。 ブロックされたサイトのカテゴリには、成人コンテンツ、娯楽サイト、法的責任サイトなどがあります。 このレポートにアクセスするには、ナビゲーション ウィンドウで [ **レポート** > **エンドポイント** > **Web 保護**] を選択します。<br/><br/>会社の Web 保護をまだ構成していない場合は、レポート ビューの **[設定]** ボタンを選択します。 次に、[ **ルール]** で [ **Web コンテンツ フィルター**] を選択します。 Web コンテンツ のフィルター処理の詳細については、「 [Web コンテンツ のフィルター処理](../defender-endpoint/web-content-filtering.md)」を参照してください。 |
| **ファイアウォール** | ファイアウォール レポートには、受信、送信、およびアプリの接続がブロックされています。 また、このレポートには、複数のデバイスで接続されたリモート IP と、接続試行回数が最も多いリモート IP も表示されます。 <br/><br/>まだファイアウォール保護を構成していない場合は、ナビゲーション ウィンドウで [**Endpoints** >  Configuration management Device configuration] (エンドポイント **構成管理** > **デバイス構成**) を選択します。 詳細については、「 [Defender for Business のファイアウォール」を](mdb-firewall.md)参照してください。 |
| **デバイス コントロール** | デバイス制御レポートには、組織内のリムーバブル ストレージ デバイスの使用など、メディアの使用状況に関する情報が表示されます。 |


## <a name="see-also"></a>関連項目

- [Defender for Business の使用を開始する](mdb-get-started.md)
- [Defender for Business でインシデントを表示および管理する](mdb-view-manage-incidents.md)
- [Defender for Business でデバイスを管理する](mdb-manage-devices.md)
