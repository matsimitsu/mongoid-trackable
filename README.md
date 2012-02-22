Mongoid::Trackable


In model

````
class HotelRoom
  Include Mongoid::Document
  include Mongoid::Trackable

end
````

Then call `hit(:action)` where :action could be anything
from :visits to :bookings


Internal structure:

````
{
  _id => BSON::ObjectId(),
  'hotel_room_id' => BSON::ObjectId(),
  'year' => 2012,
  'visits' => {
    'total' => 95,
    'months' => {
      '01' => 22,
      '02' => 33,
      '03' => 44,
      '04' => 01
    },
    'days' => {
      '01' => 10,
      '02' => 10,
      '03' => 20
    },
    'bookings' => {
      'total' => 95,
      'months' => {
        '01' => 22,
        '02' => 33,
        '03' => 44,
        '04' => 01
      },
      'days' => {
        '01' => 10,
        '02' => 10,
        '03' => 20
      }
  }
}
````
