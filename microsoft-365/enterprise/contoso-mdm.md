---
title: Contoso 社のモバイル デバイス管理
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft 365 Enterprise で Intune を使用して、デバイスやデバイスで実行されるアプリをどのように管理しているかを説明します。
ms.openlocfilehash: 9f3db160b01a54afa3457703b0333be1ff3a02ec
ms.sourcegitcommit: d9b462e035416bfa4b3d42467902c75859c55381
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "36054989"
---
# <a name="mobile-device-management-for-contoso"></a>Contoso 社のモバイル デバイス管理

**概要:** Contoso 社が Microsoft 365 Enterprise で Intune を使用して、デバイスやデバイスで実行されるアプリをどのように管理しているかを説明します。

Microsoft 365 Enterprise には、Microsoft Intune と一連の Azure サービスが含まれており、モバイル デバイスとアプリケーションの管理およびセキュリティをサポートします。

Contoso 社にはモバイル端末を使用する従業員が多く在籍しており、Contoso 社の場所にオフィスがある者もいれば、オフィスを持たない者もいます。Contoso 社では、従業員の生産性を高めつつ、デバイス、デバイスに保存される Contoso 社のデータ、およびアプリケーションの動作に関して何らかの方法でセキュリティを維持する必要があります。

## <a name="plan"></a>計画

Contoso 社は、Microsoft 365 Enterprise 向けのモバイル デバイス管理について分析した初期段階で、次の方法で Intune を使用することを確認しました。

- Exchange Online のメールとデータを保護し、モバイル デバイスから安全にアクセスできるようにします。
- Contoso 社の従業員向けに、BYOD (Bring your own Device) プログラムを実装します。
- Contoso 社の従業員向けに、組織が所有するスマート フォンや、用途が限定された共有タブレットを支給します。

Contoso 社は、次の用途では Intune を使用しません。

- 管理対象ではない公共のキオスクから従業員が Office 365 に安全にアクセスできるようにする。
- オンプレミスの Microsoft Exchange サーバーがなくなったことに伴い、オンプレミスのメールとデータを保護し、モバイル デバイスからこれらに安全にアクセスできるようにする。

## <a name="deploy"></a>展開

Contoso 社は、次のようにモバイル デバイス管理インフラストラクチャをセットアップしています。

- Intune をモバイル デバイス管理 (MDM) 機関として設定し、Azure 上で Intune を使用してコンテンツとデバイスを管理しています。
- 登録するデバイス用の Azure AD グループ、および Intune 設定とデバイスベースの条件付きアクセス ポリシーを作成しています。

  詳しくは、[Contoso 社の条件付きアクセス ポリシー](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)に関するページをご覧ください。

- iPad、iMac、iPhone、および会社所有の iPhone ベースの電話を使用する従業員をサポートするため、Apple デバイス プラットフォームを有効にしています。
- Contoso 社では、独自の使用条件ポリシーを作成しており、Contoso 社の会社ポータルをモバイル デバイスにインストールする時に表示されるようになっています。
- 未登録デバイスについては、一連のモバイル アプリケーション管理 (MAM) ポリシーにより、Office 365 サービスにアクセスするための認証が要求されます。
- 以下のための Intune ポリシーが作成されています。
  - 許可されているアプリ
  - 不正アクセスを防止するためのデバイスの暗号化
  - 6 桁の暗証番号 (PIN) またはパスワード
  - 休止状態によるタイムアウト時間
  - Windows 10 デバイス上で Windows Defender を使用した、ウイルス対策とマルウェア保護、および署名の更新
  - 最新のセキュリティ更新プログラムを含む Windows 10 デバイス上の自動更新
  - 管理対象デバイスへの証明書のプッシュ
  - ビジネス データと個人データの明確な分離。ユーザーまたは管理者は、画像、個人用メール アカウント、個人用ファイルなどの個人データはそのままにして、デバイスから会社のデータを選択的に消去できます。

これらの展開後に、Contoso 社は PC や会社所有のスマートフォンとタブレットを適切な Intune デバイス グループに追加して登録し、従業員向けに BYOD プログラムをロールアウトして従業員が個人用デバイスを登録できるようにしました。登録されたデバイスには Intune ポリシーが適用され、デバイスとそのアプリケーションは管理対象としてセキュリティ保護されています。未登録デバイスにはモバイル アプリケーション管理 (MAM) ポリシーが適用され、許可されているアプリケーションが指定されます。

## <a name="next-step"></a>次の手順

Contoso 社が Microsoft 365 Enterprise の情報保護機能を利用して、重要なデジタル資産を組織全体でどのように分類、識別、保護しているかを[説明](contoso-info-protect.md)します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のモバイル デバイス管理](mobility-infrastructure.md)

[展開ガイド](deploy-microsoft-365-enterprise.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

