---
title: Windows 10 デバイスに Microsoft Whiteboard を展開する
ms.author: chucked
author: chuckedmonson
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Windows 10 以降のバージョンを実行しているデバイスに Microsoft Whiteboard を展開する方法について説明します。
ms.openlocfilehash: 31341bc446313c54d95e14efdf569ba6e0b5263f
ms.sourcegitcommit: 24827a509b3e78959ce67679646e572a0c996282
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66917191"
---
# <a name="deploy-microsoft-whiteboard-on-windows-10-devices"></a>Windows 10 デバイスに Microsoft Whiteboard を展開する

ホワイトボードは、Microsoft Intuneまたは Microsoft Configuration Manager (以前はSystem Center Configuration Manager) を使用して、Windows 10以降を実行するデバイスに展開できます。 Windows Server ではホワイトボードはサポートされていません。

- **オンライン ライセンス モードを使用するMicrosoft Intune** – このプロセスでは、Whiteboard アプリへのアクセスを受け取るユーザーのグループを指定できます。

- **Microsoft Configuration Manager手動のオフライン インストールと更新プログラムを使用** します。このプロセスでは、Whiteboard をインストールし、2 ~ 4 週間ごとに手動で更新できます。

>[!NOTE]
> Microsoft Intuneを使用することをお勧めします。 Microsoft Configuration Managerを使用するには、ユーザーが最新バージョンを実行していることを確認するために、IT が継続的に更新プログラムを再パッケージ化してインストールする必要があります。

## <a name="install-whiteboard-using-microsoft-intune"></a>Microsoft Intuneを使用して Whiteboard をインストールする

1. 「[Microsoft Store アプリをMicrosoft Intuneに追加](/mem/intune/apps/store-apps-windows)する」の手順を使用して、使用可能なアプリとして Whiteboard を追加します。

2. この記事の手順を使用して、アプリをグループ[に割り当てます:Microsoft Intuneを持つグループにアプリを割り当てます](/mem/intune/apps/apps-deploy)。

## <a name="install-whiteboard-using-microsoft-configuration-manager"></a>Microsoft Configuration Managerを使用して Whiteboard をインストールする

1. グローバル管理者アカウントを使用して、ビジネス向け Microsoft Storeにサインイン[します](https://businessstore.microsoft.com)。

2. ヘッダーで [ **管理**] を選択します。

3. 右側のナビゲーション ウィンドウで [ **設定]** を選択し、[ **オフライン アプリの表示**] をオンにします。

4. 伝達まで 10 ~ 15 分待ちます。

5. 次に、 [ホワイトボード アプリ](https://businessstore.microsoft.com/store/details/microsoft-whiteboard/9mspc6mp8fm4)に移動します。

6. [ **アプリの取得]** を選択し、ライセンス条項に同意します。

7. アプリケーション ページに戻るします。

8. [ **ライセンスの種類** ] ドロップダウン メニューで、[オフライン] を選択 **します**。

9. **[管理]** を選択します。

10. この操作を実行すると、インベントリ管理ページに移動し、 **オフラインで使用するためにパッケージをダウンロード** するオプションが提供されます。

11. アーキテクチャのバージョンを選択し、ダウンロードします。

12. アプリをダウンロードしたらすぐに、Configuration Managerを使用してアプリをデプロイできます。 更新プログラム パッケージを作成するには、手順 7 ~ 10 に従って新しいバージョンをダウンロードし、Configuration Manager用にパッケージ化します。

13. 詳細については、 [デバイスのアプリケーションのインストールに関するページを参照してください](/mem/configmgr/apps/deploy-use/install-app-for-device)。

## <a name="see-also"></a>関連項目

[ホワイトボードへのアクセスを管理する](manage-whiteboard-access-organizations.md)

[Whiteboard のデータを管理する](manage-data-organizations.md)

[ホワイトボードの共有を管理する](manage-sharing-organizations.md)

