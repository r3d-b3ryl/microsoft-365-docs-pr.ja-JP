---
title: Microsoft マネージド デスクトップ用に、印刷リソースを準備する
description: 印刷がスムーズに機能するようにするための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1588a2c91bcbe0bd381acb6be4f9bd5562810860
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530249"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に、印刷リソースを準備する

Microsoft マネージドデスクトップに登録する準備ができたら、印刷要件を評価し、環境に適したアプローチを決定する必要があります。 次の3つのオプションがあります。
 
- Microsoft ハイブリッドクラウド印刷ソリューションを展開して、Microsoft の管理されたデスクトップデバイスでプリンターを簡単に検出できるようにします。 詳細については、「 [Deploy Windows Server ハイブリッド Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)」を参照してください。
- カスタム PowerShell スクリプトを使用して、プリンターを直接展開します。 この操作を行うには、[[ローカルプリンターの設定](#set-up-local-printers)] セクションの手順に従います。
- Azure Active Directory ドメインに参加している Windows 10 デバイスと互換性のある Microsoft 以外のクラウド印刷ソリューションを使用します。 ソリューションは、Microsoft マネージドデスクトップのソフトウェア要件を満たしている必要があります。 詳細については、「 [Microsoft Managed Desktop app の要件](../service-description/mmd-app-requirements.md)」を参照してください。
 
いずれの場合も、Microsoft Update または Microsoft ストアからプリンタードライバーを入手できない場合は、microsoft Intune を使用して Microsoft の管理されたデスクトップデバイスに展開するためにパッケージ化してパッケージ化する必要があります。 詳細については、「 [Intune スタンドアロン-Win32 app management](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management) 」を参照してください。

## <a name="set-up-local-printers"></a>ローカルプリンターをセットアップする

カスタム PowerShell スクリプトを使用してプリンターを展開し、印刷リソースを準備している場合は、次の手順に従って共有プリンターを展開します。

1.  Microsoft マネージドデスクトップポータルに移動します。
2.  管理ポータルの [ **support > support requests** ] セクションで、[*プリンター展開*] というラベルの付いた要求を送信し、次の詳細情報を提供します。
    - Microsoft マネージドデスクトップデバイス用に展開する必要がある共有プリンターの場所へのすべての UNC パス
    - これらの共有プリンターにアクセスする必要があるユーザーグループ
3.  管理ポータルを使用すると、要求が完了したことが通知されます。 最初は、テスト展開グループのデバイスにのみ構成を展開します。
4.  構成が予想どおりに動作するかどうかをテストし、確認する必要があります。 [返信] サポート要求の [**ディスカッション**] タブを使用して、テストが完了したときに通知します。
5.  その後、構成を他の展開グループに展開します。
