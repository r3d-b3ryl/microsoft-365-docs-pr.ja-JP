---
title: Microsoft マネージド デスクトップ用に、印刷リソースを準備する
description: 印刷がスムーズに機能するための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: a66075637a15eb39eda38e318070af2bcbdc8fe6
ms.sourcegitcommit: d4797cfc15c732f1a7ef21e4f944e672a7170f9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2022
ms.locfileid: "62444523"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に、印刷リソースを準備する

Microsoft Managed Desktop に登録する準備が整ったら、印刷要件を評価し、環境に適切なアプローチを決定する必要があります。 次の 3 つのオプションがあります。

| オプション | 説明 |
| ------ | ------ |
| Microsoft ユニバーサル 印刷ソリューションの展開 | Microsoft Managed Desktop デバイスがプリンターを簡単に検出するための Microsoft ユニバーサル 印刷ソリューション。 詳細については、「 [What is Universal Print」を参照してください](/universal-print/fundamentals/universal-print-whatis)。 |
| カスタム PowerShell スクリプトを使用してプリンターを直接展開する | 「ローカル プリンターのセットアップ [」セクションの手順に従](#set-up-local-printers) います。 |
| Microsoft 以外のクラウド印刷ソリューションを使用する | Microsoft 以外のクラウド印刷ソリューションを使用します。このソリューションは、デバイスと互換性があり、Windows 10ドメインにAzure Active Directoryします。 ソリューションは、Microsoft Managed Desktop のソフトウェア要件を満たす必要があります。 詳細については、「 [Microsoft Managed Desktop アプリの要件」を参照してください](../service-description/mmd-app-requirements.md)。 |

上記のすべてのオプションで、プリンター ドライバーが Microsoft Update または Microsoft Store から利用できない場合は、それらを入手し、Microsoft Intune を使用して Microsoft Managed Desktop デバイスに展開するためにパッケージ化する必要があります。 詳細については、「 [Intune スタンドアロン - Win32 アプリ管理」を参照してください。](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>ローカル プリンターのセットアップ

次の手順では、印刷リソースを準備し、カスタム PowerShell スクリプトを使用してプリンターを展開することを決めたと仮定します。

**カスタム PowerShell スクリプトを使用してプリンターを展開するには、次のコマンドを実行します。**

1. Microsoft Managed Desktop ポータルに移動します。
1. 管理ポータルの [サポート  >**要求**] セクションで、[プリンターの展開] というラベルの付いた要求を送信します。
1. 次の詳細を入力します。
    - Microsoft Managed Desktop デバイスに展開する必要がある、共有プリンターの場所へのすべての UNC パス。
    - これらの共有プリンターへのアクセスを必要とするユーザー グループ。
1. 管理ポータルを使用して、要求がいつ完了したのかお知らせします。 最初は、テスト展開グループ内のデバイスにのみ構成を展開します。
1. 構成が期待通り動作するかどうかをテストして確認します。
1. サポート要求の [ **ディスカッション]** タブを使用して返信し、テストが完了したらお知らせします。
1. その後、構成を他の展開グループに展開します。

## <a name="steps-to-get-ready"></a>準備の手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
1. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. [アプリを準備します](apps.md)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. 印刷リソースを準備する (この記事)。
1. [デバイス名](address-device-names.md)をアドレス指定します。
