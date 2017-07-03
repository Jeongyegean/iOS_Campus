# MapView

## A. 용어

***

• Region : 지역 (MKCoordinateRegion사용)<p>
***

- Spen 부연설명: 지도는 이미지다. 확대하다보면 좀 더 디테일한 이미지로 바꾸어서 다시 로드해주는 것
	- Region이라는 한 화면에 10km까지 보여줄거야 또는 1km까지 보여줄거야 라는 방식으로 설정해서 이미지를 확대할 수도 있다.
- 위도와 경도로 좌표(Location Coordinate)를 만든다
- Span과 거리를 가지고 Region을 만든다.
- 지도를 움직이면 위도경도가 계속 바뀌는 것이고, 지도를 확대축소하면 Span이 바뀌는 것이다.

## B. Center 좌표 설정

```swift
let regionRadius: CLLocationDistance = 1000


```

- latitude: 가로선 | longitute: 세로선
- Distance의 기준은 meter다. 

```swift
//setLocation Location

```

## C. Pin 추가 

***

• MKAnnotation Protocol을 사용하여 annotation 클래스 생성(NSObject 필수 상속)<p>
***

- annotation은 UI가 아니고, 데이터다.
- annotation View가 실질적으로 보인다.

```swift
public protocol MKAnnotation : NSObjectProtocol {
```

## D. MKMapViewDelegate

```swift
func mapView(_ mapView: MKMapView, viewFor annotation: MKAnnotation) -> MKAnnotationView? {

```

## E. 사용자 위치 설정

***

**• 사용자 허용**<p>


```





***

- 반드시 map과 써야하는 것은 아니다.
- 쓰려면 사용자에게 위치서비스 허용을 받아야 한다.

```swift
let manager = CLLocationManager()
mapView.showsUserLocation
```