---
title: Microsoft Defender ウイルス対策通知の構成
description: エンドポイントで標準通知と追加Microsoft Defender ウイルス対策通知の両方を構成およびカスタマイズする方法について説明します。
keywords: 通知, 擁護者, ウイルス対策, エンドポイント, 管理, 管理者
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572347"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>エンドポイントに表示される通知を構成する

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Windows 10では、マルウェアの検出と修復に関するアプリケーション通知がより堅牢で、一貫性があり、簡潔になります。

手動でトリガーされ、スケジュールされたスキャンが完了し、脅威が検出されると、エンドポイントに通知が表示されます。 これらの通知は **通知センター** にも表示され、スキャンと脅威検出の概要は一定の間隔で表示されます。

また、再起動の通知や脅威が検出および修復された場合など、エンドポイントでの標準通知の表示方法を構成することもできます。

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>エンドポイントに表示される追加の通知を構成する

最新の脅威検出の概要などの追加の通知の表示は[、Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md)とグループ ポリシーで構成できます。

> [!NOTE]
> Windows 10 バージョン 1607 では、この機能は **拡張通知** と呼ばれ  >  **、Windows 設定 Update & セキュリティ**  >  **Windows Defender** で構成できます。 すべてのバージョンのWindows 10のグループ ポリシー設定では、**拡張通知** と呼ばれます。

> [!IMPORTANT]
> 追加の通知を無効にしても、脅威の検出や修復のアラートなどの重要な通知は無効にされません。

**Windows セキュリティ アプリを使用して、追加の通知を無効にします。**

1. タスク バーの盾アイコンをクリックするか、または [**セキュリティ**] の [スタート] メニューを検索して、Windows セキュリティ アプリを開きます。

2. [**ウイルス&脅威対策** タイル(または左側のメニュー バーの盾アイコン)を選択し、[**ウイルス&脅威対策の設定**] を選択します。

3. [ **通知** ] セクションまでスクロールし、[ **通知設定の変更**] をクリックします。

4. スイッチを **[オフ]** または **[オン] に** スライドして、追加の通知を無効または有効にします。

**グループ ポリシーを使用して、追加の通知を無効にする:**

1. グループ ポリシー管理コンピュータで、[グループ [ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))] を開き、構成するグループ ポリシー オブジェクトを右クリックして 、[ **編集**] をクリックします。

2. グループ **ポリシー管理エディタ** で、[ **コンピュータの構成]** に移動します。

3. [ **管理用テンプレート**] をクリックします。

4. ツリーを展開して **コンポーネントをWindows> Microsoft Defender ウイルス対策 >レポート** を作成します。

5. [ **拡張通知をオフにする** ] をダブルクリックし、オプションを **[有効]** に設定します。 [**OK**] をクリックします。 これにより、追加の通知が表示されなくなります。

## <a name="configure-standard-notifications-on-endpoints"></a>エンドポイントでの標準通知の構成

グループ ポリシーを使用すると、次のことができます。

- ユーザーがアクションを実行する必要がある場合にエンドポイントに追加のカスタマイズテキストを表示する
- エンドポイントのすべての通知を非表示にする
- エンドポイントでの再起動通知を非表示にする

通知を非表示にすると、Microsoft Defender ウイルス対策インターフェイス全体を非表示にできない場合に便利です。 詳細については[、「Microsoft Defender ウイルス対策ユーザー インターフェイスをユーザーが表示したり、操作したりできないように](prevent-end-user-interaction-microsoft-defender-antivirus.md)する」を参照してください。 

> [!NOTE]
> 通知を非表示にするのは、ポリシーが展開されているエンドポイントでのみ発生します。 実行する必要があるアクションに関連する通知 (再起動など) は[、Microsoft エンドポイント マネージャー Endpoint Protection監視ダッシュボードとレポート](/configmgr/protect/deploy-use/monitor-endpoint-protection)に表示されます。 

ユーザーが自分のコンピューターに表示される通知にカスタム連絡先情報を追加する手順については、「[組織のWindows セキュリティアプリをカスタマイズ](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)する」をご覧ください。

**グループ ポリシーを使用して通知を非表示にする:**

1. グループ ポリシー管理コンピュータで、グループ [ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシー オブジェクトを右クリックして、[ **編集**] をクリックします。

2. グループ **ポリシー管理エディタ** で[ **コンピュータの構成]** に移動し、[ **管理用テンプレート**]をクリックします。

3. ツリーを展開して **、クライアント インターフェイス> Microsoft Defender ウイルス対策 >コンポーネントをWindows** します。 

4. [ **すべての通知を抑制** する] をダブルクリックし、オプションを **[有効]** に設定します。 [**OK**] をクリックします。 これにより、追加の通知が表示されなくなります。

**グループ ポリシーを使用して再起動通知を非表示にする:**

1. グループ ポリシー管理コンピュータで、[グループ [ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))] を開き、構成するグループ ポリシー オブジェクトを右クリックして 、[ **編集**] をクリックします。

2. グループ **ポリシー管理エディタ** で、[ **コンピュータの構成]** に移動します。

3. [ **管理用テンプレート**] をクリックします。

4. ツリーを展開して **、クライアント インターフェイス> Microsoft Defender ウイルス対策 >コンポーネントをWindows** します。

5. [ **再起動通知を抑制する** ] をダブルクリックし、オプションを **[有効]** に設定します。 [**OK**] をクリックします。 これにより、追加の通知が表示されなくなります。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender ウイルス対策とのエンド ユーザーの対話を構成する](configure-end-user-interaction-microsoft-defender-antivirus.md)
