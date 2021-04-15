---
title: Microsoft Defender ウイルス対策通知の構成
description: エンドポイントで標準の Microsoft Defender ウイルス対策通知と追加の Microsoft Defender ウイルス対策通知の両方を構成およびカスタマイズする方法について説明します。
keywords: 通知, Defender, ウイルス対策, エンドポイント, 管理, 管理者
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a91da48f27450d6f4a6fd2b9607aa979458ccf71
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765097"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>エンドポイントに表示される通知を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Windows 10 では、マルウェアの検出と修復に関するアプリケーション通知の信頼性が高く、一貫性があり、簡潔になります。

手動でトリガーされ、スケジュールされたスキャンが完了し、脅威が検出されると、エンドポイントに通知が表示されます。 これらの通知は通知センター **にも表示** され、スキャンと脅威検出の概要は一定の間隔で表示されます。

また、再起動の通知や脅威が検出され修復された場合など、エンドポイントでの標準通知の表示方法を構成することもできます。

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>エンドポイントに表示される追加の通知を構成する

Windows セキュリティ アプリとグループ ポリシーで、最近の脅威検出の概要などの追加の通知の [表示を構成](microsoft-defender-security-center-antivirus.md) できます。

> [!NOTE]
> Windows 10 バージョン 1607 では、この機能は拡張通知と呼ばされ **、Windows 設定** 更新プログラムの [セキュリティ 更新プログラム&  >  **構成**  >  Windows Defender。 Windows 10 のすべてのバージョンのグループ ポリシー設定では、拡張通知と **呼ばれる。**

> [!IMPORTANT]
> 追加の通知を無効にすると、脅威の検出や修復アラートなどの重要な通知は無効にされません。

**Windows セキュリティ アプリを使用して、追加の通知を無効にします。**

1. タスク バーのシールド アイコンをクリックするか、Defender のスタート メニューを検索して、Windows セキュリティ アプリを開 **きます**。

2. [ウイルス **対策]** &タイル (または左側のメニュー バーのシールド アイコン) をクリックし、[ウイルス対策] &設定ラベルを **クリック** します。

    ![Windows セキュリティ アプリの [ウイルス&保護設定] ラベルのスクリーンショット](images/defender/wdav-protection-settings-wdsc.png)

3. [通知] セクションまで **スクロールし** 、[通知設定の **変更] をクリックします**。

4. スイッチを Off または **On にスライド****して**、追加の通知を無効または有効にします。

**グループ ポリシーを使用して、追加の通知を無効にします。**

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [管理 **用テンプレート] をクリックします**。

4. ツリーを **Microsoft Defender ウイルス対策レポート> Windows コンポーネント>展開します**。

5. [拡張通知を **オフにする] をダブルクリック** し、オプションを [有効] に **設定します**。 **[OK]** をクリックします。 これにより、追加の通知が表示されません。

## <a name="configure-standard-notifications-on-endpoints"></a>エンドポイントの標準通知を構成する

グループ ポリシーを使用すると、次の場合に使用できます。

- ユーザーがアクションを実行する必要がある場合に、エンドポイントに追加のカスタマイズされたテキストを表示する
- エンドポイントのすべての通知を非表示にする
- エンドポイントで再起動通知を非表示にする

通知の非表示は、Microsoft Defender ウイルス対策インターフェイス全体を非表示にできない状況で役立ちます。 詳細 [については、「ユーザーによる Microsoft Defender ウイルス](prevent-end-user-interaction-microsoft-defender-antivirus.md) 対策ユーザー インターフェイスの表示または操作を防止する」を参照してください。 

> [!NOTE]
> 通知の非表示は、ポリシーが展開されたエンドポイントでのみ発生します。 実行する必要があるアクション (再起動など) に関連する通知は、引き続き Microsoft Endpoint Manager Endpoint Protection の監視 [ダッシュボードとレポートに表示されます](/configmgr/protect/deploy-use/monitor-endpoint-protection)。 

ユーザー [が自分のコンピューターに](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 表示する通知にカスタム連絡先情報を追加する手順については、「組織の Windows セキュリティ アプリをカスタマイズする」を参照してください。

**グループ ポリシーを使用して通知を非表示にする:**

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。

3. Microsoft Defender Antivirus > **クライアント インターフェイス>ツリーを展開します**。 

4. [すべての通知を **非表示にする] をダブルクリック** し、オプションを [有効] に **設定します**。 **[OK]** をクリックします。 これにより、追加の通知が表示されません。

**グループ ポリシーを使用して再起動通知を非表示にします。**

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [管理 **用テンプレート] をクリックします**。

4. Microsoft Defender Antivirus > **クライアント インターフェイス>ツリーを展開します**。

5. [再起動通知を **抑制する] をダブルクリックし** 、オプションを [有効] に **設定します**。 **[OK]** をクリックします。 これにより、追加の通知が表示されません。

## <a name="related-topics"></a>関連項目

- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender ウイルス対策とのエンド ユーザー操作を構成する](configure-end-user-interaction-microsoft-defender-antivirus.md)