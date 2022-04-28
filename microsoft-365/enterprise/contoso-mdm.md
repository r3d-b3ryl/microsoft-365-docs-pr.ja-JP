---
title: Contoso 社のモバイル デバイス管理
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso がエンタープライズ向けのMicrosoft 365でMicrosoft Intuneを使用して、デバイスとそのデバイスで実行されるアプリを管理する方法について説明します。
ms.openlocfilehash: c321fc9bdaf27577e32d934aa771c92d1a0bdd79
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092693"
---
# <a name="mobile-device-management-for-contoso"></a>Contoso 社のモバイル デバイス管理

企業向けのMicrosoft 365には、モバイル デバイスとアプリケーションの管理とセキュリティをサポートするIntuneと Azure サービスのセットが含まれます。

Contoso には、モバイル対応の従業員が多数います。 一部のオフィスは Contoso の場所にあり、一部にはオフィスがありません。 Contoso は、従業員の生産性を有効にする方法が必要でしたが、デバイス、それらのデバイスに格納されている Contoso データ、およびアプリケーションの動作をセキュリティで保護します。

## <a name="plan"></a>計画

Contoso は、エンタープライズ向けのMicrosoft 365のモバイル デバイス管理の次のIntuneユース ケースを特定しました。

- モバイル デバイスから安全にアクセスできるように、Exchange Online電子メールとデータを保護します。
- Contoso 従業員用の持ち込みデバイス (BYOD) プログラムを実装します。
- 組織所有の電話と使用制限付き共有タブレットを Contoso の従業員に発行します。

Contoso は、次のIntuneを使用しません。

- 従業員が管理されていないパブリック キオスクからMicrosoft 365に安全にアクセスできるようにします。
- オンプレミスの Microsoft Exchange サーバーがないため、モバイル デバイスから安全にアクセスできるように、オンプレミスの電子メールとデータを保護します。

## <a name="deploy"></a>展開

Contoso 社は、次のようにモバイル デバイス管理インフラストラクチャをセットアップしています。

- Intuneモバイル デバイス管理 (MDM) 機関として設定し、Azure でIntuneを使用してコンテンツを管理し、デバイスを管理する
- 登録とIntuneの設定とデバイス ベースの条件付きアクセス ポリシー用にデバイスのAzure Active Directory (Azure AD) グループを作成しました

  詳細については、「 [Contoso 条件付きアクセス ポリシー](contoso-identity.md#conditional-access-policies-for-zero-trust-identity-and-device-access)」を参照してください。

- Apple デバイス プラットフォームで、iPad、iMac、iPhone、企業所有の iPhone を使用して従業員をサポートできるようになりました
- Contoso 社では、独自の使用条件ポリシーを作成しており、Contoso 社の会社ポータルをモバイル デバイスにインストールする時に表示されるようになっています。
- 登録されていないデバイスの場合、Microsoft 365 サービスへのアクセスに認証を要求する一連のモバイル アプリケーション管理 (MAM) ポリシーが実装されました
- 以下のための Intune ポリシーが作成されています。
  - 許可されたアプリ。
  - 承認されていないアクセスを防ぐのに役立つデバイス暗号化。
  - 6 桁の PIN またはパスワード。
  - 非アクティブタイムアウト期間。
  - Windows 10 デバイス上のWindows Defenderによるウイルス対策とマルウェアの保護、および署名の更新。
  - 最新のセキュリティ更新プログラムを含むWindows 10 デバイスの自動更新。
  - マネージド デバイスへの証明書のプッシュ。
  - ビジネス データと個人データの明確な分離。ユーザーまたは管理者は、画像、個人用メール アカウント、個人用ファイルなどの個人データはそのままにして、デバイスから会社のデータを選択的に消去できます。

Contoso は、適切なIntuneデバイス グループに追加することで、展開された PC と会社所有のスマートフォンとタブレットを登録しました。 また、従業員が個人用デバイスを登録するための BYOD プログラムも確立しました。 登録されたデバイスはIntuneポリシーを受け取り、その結果、デバイスとそのアプリケーションが管理され、セキュリティで保護されます。 登録されていないデバイスには、許可されたアプリケーションを指定するモバイル アプリケーション管理 (MAM) ポリシーがあります。

Contoso モバイル デバイス管理のデプロイ アーキテクチャを次に示します。

![Contoso モバイル デバイス管理のデプロイ インフラストラクチャ。](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>次の手順

Contoso がエンタープライズ向けにMicrosoft 365の[情報保護機能](contoso-info-protect.md)を使用して、組織全体で重要なデジタル資産を分類、識別、保護する方法について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365のデバイス管理](device-management-roadmap-microsoft-365.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

